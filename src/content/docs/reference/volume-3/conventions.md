---
title: "Conventions and Notation"
description: "Symmetry, current, background-field, anomaly, topological-term, and defect conventions used in the Symmetry, Anomalies, and Topology volume."
sidebar:
  label: "Conventions and Notation"
  order: 1
level: Graduate
status: "Polished draft"
source: "Site-wide conventions; Coleman, Srednicki, Weinberg, Zee, Schwartz; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - conventions
  - currents
  - background fields
  - anomalies
  - topological terms
  - defects
canonicalTopics:
  - symmetry-conventions
  - anomaly-conventions
  - topological-term-normalization
researchStatus:
  established:
    - "The metric, Fourier, Noether-current, background-field, and differential-form conventions on this page are standard, but many signs differ across textbooks."
  active:
    - "Higher-form, non-invertible, and symmetry TFT notation is still less uniform across the literature; pages using sharper categorical conventions will state them locally."
---

## Summary

This page fixes the conventions used in this volume beyond the site-wide spacetime, Fourier, spinor, and path-integral conventions. Unless a page says otherwise, we use mostly-minus Lorentzian signature,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1,
\qquad
f(x)=\int\frac{d^dp}{(2\pi)^d}e^{-ip\cdot x}\widetilde f(p).
$$

The additional choices made here are the ones that most often create silent sign errors in symmetry and anomaly calculations: active versus passive transformations, the sign of the charge action, Hermitian versus anti-Hermitian generators, the normalization of background fields, descent conventions, orientation conventions, and factors of $2\pi$ in topological terms.

The compact rule is:

$$
U(\alpha)=e^{-i\alpha^a Q_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O],
\qquad
D=d-iA,
\qquad
D^2=-iF.
$$

If a later page uses a different convention because a standard reference does, it will say so before any convention-sensitive formula.

## Prerequisites

You should be comfortable with Lorentz indices, differential forms, Lie algebra generators, path-integral generating functionals, and the idea that QFT correlators can contain contact terms. For orientation, first read the [volume overview](/symmetry-anomalies-topology/). No knowledge of anomaly polynomials, Chern–Simons theory, or higher-form symmetry is assumed here.

## Core idea

Conventions in symmetry theory are not cosmetic. They determine whether the Ward identity has a plus or minus sign, whether a current is defined by $\delta W/\delta A$ or $-\delta W/\delta A$, whether $F=dA-iA\wedge A$ or $F=dA+A\wedge A$, whether a Chern–Simons level is integral, and whether an anomaly is written as $\delta W=2\pi\int I_d^{(1)}$ or $\delta\log Z=2\pi i\int I_d^{(1)}$.

The strategy in this volume is to make every convention locally checkable. A reader should be able to recover the sign of a Ward identity by integrating it across a time slice, the normalization of an anomaly by varying the background effective action, and the normalization of a topological term by checking the phase $e^{iS}$ under large gauge transformations.

## Setup and conventions

Spacetime dimension is denoted by $d$ unless a page specializes to four dimensions. Lorentzian spacetime is $M_d$ and Euclidean spacetime is usually $X_d$. A closed oriented $k$-manifold or cycle is written $\Sigma_k$, $C_k$, or $M_k$ depending on context.

We use differential forms heavily. For a $p$-form $\omega$,

$$
\omega=\frac{1}{p!}\omega_{\mu_1\cdots\mu_p}
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p}.
$$

The exterior derivative satisfies $d^2=0$. Wedge products are graded:

$$
\alpha_p\wedge\beta_q=(-1)^{pq}\beta_q\wedge\alpha_p.
$$

The Hodge star $\star$ depends on the metric and orientation. When a sign depends on Lorentzian versus Euclidean signature, the page doing the calculation will state the version being used.

:::caution[Convention-sensitive formulas]
Many anomaly and topological-term formulas differ by signs between Hermitian-generator and anti-Hermitian-generator conventions. This volume uses Hermitian generators by default. When comparing to mathematics references, expect $A_{\mathrm{math}}=-iA_{\mathrm{here}}$ and $F_{\mathrm{math}}=-iF_{\mathrm{here}}$.
:::

## Symmetry transformations and charges

For an ordinary internal continuous symmetry group $G$, generators $Q_a$ act on states through

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

For an operator $\mathcal O(x)$, we define the infinitesimal active variation by

$$
\delta_\alpha\mathcal O(x)
\equiv U(\alpha)^\dagger\mathcal O(x)U(\alpha)-\mathcal O(x)
=\alpha^a\delta_a\mathcal O(x)+O(\alpha^2),
$$

so that

$$
\delta_a\mathcal O(x)=i[Q_a,\mathcal O(x)],
\qquad
[Q_a,\mathcal O(x)]=-i\delta_a\mathcal O(x).
$$

For a field multiplet $\Phi$ in a representation $R$ of $G$, we use Hermitian representation matrices $T_a^{(R)}$ satisfying

$$
[T_a^{(R)},T_b^{(R)}]=if_{ab}^{\ \ c}T_c^{(R)}.
$$

A common linear transformation is

$$
\delta_a\Phi=iT_a^{(R)}\Phi.
$$

This choice is not universal. Some books absorb the factor of $i$ into anti-Hermitian generators. Whenever a formula depends on this choice, the page will use the commutator convention above as the reference point.

:::note[Source note]
Coleman’s lectures, Weinberg, Srednicki, Zee, and Schwartz all use closely related charge-current ideas, but they do not make identical choices for metric signature, Fourier phases, and generator hermiticity. The convention $\delta_a\mathcal O=i[Q_a,\mathcal O]$ is chosen here because it makes the integrated Ward identity match the equal-time charge action with the site-wide plane-wave convention.
:::

## Noether currents

For fields $\Phi^I$ and a continuous transformation $\delta_a\Phi^I$, suppose the Lagrangian changes by a total derivative,

$$
\delta_a\mathcal L=\partial_\mu K_a^\mu.
$$

The canonical Noether current is

$$
j_a^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\delta_a\Phi^I-K_a^\mu.
$$

On the classical equations of motion,

$$
\partial_\mu j_a^\mu=0.
$$

The corresponding charge on a constant-time slice is

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

assuming boundary conditions that make surface terms vanish.

Currents are not unique. If $B_a^{\mu\nu}=-B_a^{\nu\mu}$, then

$$
j_a^\mu\longrightarrow j_a^\mu+\partial_\nu B_a^{\mu\nu}
$$

has the same local conservation law. It gives the same charge when the boundary term vanishes, but it can change contact terms, stress tensors, and couplings to background fields.

## Ward identities and contact terms

Let $\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)$. In the absence of anomalies and explicit breaking, the local Ward identity is written

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle\mathcal O_1(x_1)\cdots\delta_a\mathcal O_k(x_k)\cdots\mathcal O_n(x_n)\rangle.
$$

This sign is tied to the charge convention $\delta_a\mathcal O=i[Q_a,\mathcal O]$. Integrating the Ward identity over a thin time slab around $x_k^0$ reproduces the equal-time commutator of the charge with the operator insertion.

If the symmetry is explicitly broken by an operator $\mathcal B_a(x)$, we write

$$
\partial_\mu j_a^\mu=\mathcal B_a
$$

inside correlation functions, together with the same contact terms. If the symmetry is anomalous, the right-hand side is replaced or supplemented by a local functional of background fields.

:::caution[Contact terms are part of the identity]
A Ward identity without contact terms is usually incomplete. The contact terms are exactly what tell the current how to act on operator insertions.
:::

## Background fields

A background field is a nondynamical source coupled to an operator or symmetry current. For an ordinary continuous internal symmetry, the background gauge field is

$$
A=A_\mu^aT_a\,dx^\mu,
$$

with Hermitian generators. The covariant derivative on matter in representation $R$ is

$$
D=d-iA,
\qquad
D_\mu=\partial_\mu-iA_\mu^aT_a^{(R)}.
$$

The field strength is defined by

$$
D^2=-iF,
\qquad
F=dA-iA\wedge A.
$$

In components,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu-i[A_\mu,A_\nu].
$$

Under a finite background gauge transformation $g(x)\in G$,

$$
A\longrightarrow A^g=gAg^{-1}+ig\,dg^{-1},
\qquad
F\longrightarrow F^g=gFg^{-1}.
$$

For infinitesimal $g=e^{i\lambda}$,

$$
\delta_\lambda A=d\lambda-i[A,\lambda]\equiv D\lambda.
$$

The generating functional in a background field is normalized by

$$
Z[A]=e^{iW[A]},
\qquad
\langle j_a^\mu(x)\rangle_A=\frac{\delta W[A]}{\delta A_\mu^a(x)}.
$$

Equivalently,

$$
\langle j_a^\mu(x)\rangle_A=\frac{1}{i}\frac{\delta\log Z[A]}{\delta A_\mu^a(x)}.
$$

This fixes the sign of current insertions generated by $A$.

:::note[Source note]
The sign of the linear source term is often hidden inside the choice of covariant derivative. Here $D=\partial-iA$ and $\langle j\rangle=\delta W/\delta A$ define the convention. A later model page may derive the same current from minimal coupling and will state the charge convention for the fields explicitly.
:::

## Gauging versus coupling to backgrounds

Coupling to a background field means $A$ is a classical probe. Gauging means $A$ becomes dynamical or is summed over in the path integral, including a choice of allowed bundles, gauge transformations, and local counterterms.

The distinction is crucial:

| Operation | What is varied or summed over? | What it tests |
|---|---|---|
| Add a source | A fixed background field $A$ | Current correlators and response. |
| Couple to a background gauge field | All fixed $A$ related by background gauge transformations | Whether the global symmetry is consistently definable on nontrivial backgrounds. |
| Gauge the symmetry | Gauge-equivalence classes of $A$, often including topological sectors | Whether the symmetry has an obstruction to gauging. |

A global symmetry can exist even when it cannot be gauged. The obstruction is an ’t Hooft anomaly.

## Anomaly conventions

An anomaly of a global symmetry is recorded by the failure of the background-field effective action to be invariant. In this volume,

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A].
$$

Using $\delta_\lambda A=D\lambda$ and integrating by parts on a closed spacetime gives

$$
D_\mu\langle j_a^\mu\rangle_A=-\mathcal A_a[A].
$$

Thus $\mathcal A_a[A]$ is the local anomaly functional in the convention of this page. Some references define the anomaly with the opposite sign.

For perturbative anomalies described by descent, we write an anomaly polynomial $I_{d+2}$ as

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta_\lambda I_{d+1}^{(0)}=dI_d^{(1)}(\lambda).
$$

The anomalous variation is normalized by

$$
\delta_\lambda\log Z[A]=2\pi i\int_{M_d}I_d^{(1)}(\lambda),
$$

or equivalently,

$$
\delta_\lambda W[A]=2\pi\int_{M_d}I_d^{(1)}(\lambda).
$$

:::caution[Descent signs vary]
Descent formulas are among the most convention-sensitive formulas in anomaly theory. Signs can change when one changes Hermitian to anti-Hermitian generators, reverses orientation, uses Euclidean rather than Lorentzian $W$, or defines $Z=e^{-W_E}$ instead of $Z=e^{iW}$. Always compare the phase of $Z$, not just the displayed anomaly density.
:::

## Flavor, gauge, gravitational, and mixed anomalies

We use these labels in a specific way.

| Label | Meaning in this volume |
|---|---|
| Flavor anomaly | An anomaly of a global internal symmetry, diagnosed with background flavor fields. |
| Gauge anomaly | An anomaly of a dynamical gauge redundancy; it is an inconsistency unless canceled. |
| Gravitational anomaly | An anomaly under diffeomorphisms or local Lorentz transformations, diagnosed by background geometry. |
| Mixed anomaly | An anomaly involving more than one background structure, such as flavor and gravity or zero-form and one-form symmetries. |
| ’t Hooft anomaly | Any anomaly of a global symmetry that obstructs gauging and must be matched along RG flow. |

A gauge anomaly is not a physical symmetry-breaking effect. It means the proposed gauge theory has not been consistently defined. A global or ’t Hooft anomaly, by contrast, is valid physical data of the QFT.

## Group theory normalization

For compact simple groups, generators are Hermitian. In representation $R$,

$$
\operatorname{tr}_R(T_aT_b)=T(R)\delta_{ab}.
$$

For the fundamental representation of $SU(N)$,

$$
\operatorname{tr}_{\mathrm{fund}}(T_aT_b)=\frac12\delta_{ab}.
$$

The quadratic Casimir $C_2(R)$ is defined by

$$
T_a^{(R)}T_a^{(R)}=C_2(R)\mathbf 1_R.
$$

For $SU(N)$,

$$
T(\mathrm{fund})=\frac12,
\qquad
C_2(\mathrm{fund})=\frac{N^2-1}{2N},
\qquad
C_2(\mathrm{adj})=N.
$$

The global form of a group is not determined by its Lie algebra. A page discussing line operators or background bundles will distinguish, for example, $SU(N)$ from $PSU(N)=SU(N)/\mathbb Z_N$.

## Orientation and integration

All integrals of top forms assume an orientation. Reversing the orientation of $M_d$ changes

$$
\int_{M_d}\omega_d\longrightarrow -\int_{M_d}\omega_d.
$$

For product manifolds $M_m\times N_n$, we use the product orientation in the written order. Boundary orientation follows Stokes’ theorem:

$$
\int_{M_d}d\omega_{d-1}=\int_{\partial M_d}\omega_{d-1}.
$$

On Lorentzian spacetime, the path-integral phase is $e^{iS}$. On Euclidean spacetime, the non-topological part usually appears as $e^{-S_E}$, while theta terms and Chern–Simons terms often remain phases.

## Topological terms

For a compact $U(1)$ gauge field, the flux is quantized by

$$
\frac{1}{2\pi}\int_{\Sigma_2}F\in\mathbb Z
$$

for every closed two-cycle $\Sigma_2$.

For a non-Abelian gauge field with the trace normalization above, the instanton number is written

$$
k=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F).
$$

For an $SU(N)$ bundle on a closed four-manifold, $k\in\mathbb Z$ with the usual normalization. The Lorentzian theta term contributes the phase

$$
e^{iS_\theta}=\exp(i\theta k).
$$

The Chern–Simons three-form in Hermitian-generator conventions is

$$
\operatorname{CS}_3(A)
=\operatorname{tr}\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right),
$$

with

$$
d\operatorname{CS}_3(A)=\operatorname{tr}(F\wedge F).
$$

The non-Abelian Chern–Simons action is

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int_{M_3}\operatorname{CS}_3(A).
$$

For a compact gauge group on a closed oriented three-manifold, invariance of $e^{iS_{\mathrm{CS}}}$ under large gauge transformations quantizes the level $k$. The precise quantization can depend on the global form of the gauge group and on whether the theory is defined only on spin manifolds.

:::note[Source note]
The formula for $\operatorname{CS}_3(A)$ above is adapted to Hermitian generators and $F=dA-iA\wedge A$. In anti-Hermitian conventions the cubic term is usually written without the explicit $i$, and the overall sign of the level may look different.
:::

## Fermions, spin structures, and discrete spacetime symmetries

Fermionic theories require extra geometric data. On an oriented Riemannian or Lorentzian manifold, ordinary spinors require a spin structure. Charged fermions can sometimes be defined using a spin${}_c$ structure instead. Time-reversal or reflection symmetries may require pin${}^+$ or pin${}^-$ structures, depending on how reflections square on fermions.

We write fermion parity as

$$
(-1)^F.
$$

A discrete symmetry that differs by $(-1)^F$ is generally a different symmetry. Pages on time reversal, reflection positivity, and discrete anomalies will state the relevant spin or pin structure explicitly.

## Higher-form symmetry notation

A $p$-form global symmetry in $d$ spacetime dimensions acts on $p$-dimensional charged operators. For $p=0$, the charged operators are local operators. For $p=1$, the charged operators are line operators. For $p=2$, they are surface operators.

A continuous $p$-form symmetry has a conserved $(p+1)$-form current $J_{p+1}$ satisfying

$$
d\star J_{p+1}=0.
$$

The corresponding topological symmetry operator is supported on a closed codimension-$(p+1)$ manifold $\Sigma_{d-p-1}$:

$$
U_\alpha(\Sigma_{d-p-1})
=\exp\left(i\alpha\int_{\Sigma_{d-p-1}}\star J_{p+1}\right).
$$

Topological means $U_\alpha(\Sigma_{d-p-1})$ can be deformed without changing correlation functions, as long as it does not cross charged operators or other relevant defects.

For $p>0$, the symmetry group is Abelian in ordinary higher-form symmetry. Non-Abelian-like phenomena can still appear in higher-categorical or non-invertible settings, but that requires extra structure and will be stated separately.

## Defects and extended operators

We use the following notation when no more specific convention is needed.

| Object | Typical notation | Support |
|---|---|---|
| Local operator | $\mathcal O(x)$ | point |
| Line operator | $L(C_1)$, $W_R(C_1)$, $T(C_1)$ | curve $C_1$ |
| Surface operator | $S(\Sigma_2)$ | surface $\Sigma_2$ |
| Domain wall or interface | $\mathcal D(M_{d-1})$ | codimension one |
| General defect | $\mathcal D_k(M_k)$ | $k$-manifold $M_k$ |

A genuine operator is well-defined on its support alone. A non-genuine operator must end on or be attached to another object, such as a surface, branch cut, or higher-dimensional defect. This distinction is central in discussions of line operators, discrete gauge theory, higher-form symmetry, and non-invertible defects.

## Topological operators and fusion

A topological operator is an operator whose support can be deformed without affecting correlation functions, provided the deformation avoids charged insertions and singularities. For ordinary invertible symmetry, topological operators fuse according to a group law:

$$
U_g(\Sigma)U_h(\Sigma)=U_{gh}(\Sigma),
\qquad
U_g(\Sigma)^{-1}=U_{g^{-1}}(\Sigma).
$$

For non-invertible symmetry, the fusion can be a sum or category-valued composition rather than a group product. In a schematic two-dimensional example,

$$
\mathcal N\times\mathcal N=\sum_i n_i\mathcal L_i,
\qquad
n_i\in\mathbb Z_{\ge 0}.
$$

Pages on non-invertible symmetry will specify the relevant category, defect normalization, and whether the discussion is topological, conformal, lattice, or continuum.

## Common pitfalls

**Comparing charges without comparing the operator action.** Two pages may write the same $Q$ but define $U=e^{+i\alpha Q}$ instead of $U=e^{-i\alpha Q}$. The safest comparison is the commutator with a charged operator.

**Treating a current as unique.** Improvement terms can be invisible for charges but visible for local Ward identities, stress tensors, and background-field couplings. This is especially important near trace anomalies and mixed anomalies.

**Confusing background gauge invariance with dynamical gauge redundancy.** Background gauge transformations express how sources and operators transform together. Dynamical gauge transformations identify redundant configurations in the path integral.

**Forgetting global form.** The Lie algebra determines infinitesimal transformations, but the global form determines bundles, line operators, allowed background fields, and large gauge transformations.

**Dropping spin-structure dependence.** Fermionic partition functions, time-reversal anomalies, and some Chern–Simons contact terms are not defined without specifying the relevant spin, spin${}_c$, or pin structure.

**Calling every total derivative irrelevant.** A total derivative can change the quantum theory on nontrivial spacetime, in the presence of boundaries, or when instanton sectors contribute.

## Relations to other pages

- [Volume Overview](/symmetry-anomalies-topology/) explains where these conventions are used in the reading path.
- The future Ordinary Global Symmetries chapter will use the charge convention $\delta_a\mathcal O=i[Q_a,\mathcal O]$ as its default operator convention.
- The future Background Fields and Gauging chapter will use $D=d-iA$ and $F=dA-iA\wedge A$ as its default background-field convention.
- The future Anomalies and ’t Hooft Anomalies chapters will use the descent normalization $\delta\log Z=2\pi i\int I_d^{(1)}$ unless a page explicitly changes convention.
- The future Topological Terms chapter will use the flux, instanton-number, and Chern–Simons normalizations stated here as its default lookup table.

## Research status

The ordinary symmetry, current, background-field, and topological-term conventions on this page are textbook-standard once the sign choices are fixed. The main issue is not unsettled physics but comparison across sources.

Higher-form symmetry notation is now standard enough to use throughout the volume, especially the language of topological operators supported on codimension-$(p+1)$ manifolds. Non-invertible symmetry and symmetry TFT conventions are less uniform. Pages in those chapters will include local convention boxes and source notes where definitions differ across current papers.

## Exercises

### Exercise 1: Recover the charge action from the Ward identity

Assume the Ward identity

$$
\partial_\mu\langle j_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle.
$$

Integrate over a thin time slab containing $y^0$ and show that it matches $[Q_a,\mathcal O(y)]=-i\delta_a\mathcal O(y)$.

<details>
<summary><strong>Solution</strong></summary>

Integrate over $x^0\in(y^0-\epsilon,y^0+\epsilon)$ and all spatial $\mathbf x$. The spatial divergence gives a boundary term at infinity, assumed to vanish. The left side becomes the discontinuity of the time-ordered insertion of the charge across $y^0$, which is the equal-time commutator $\langle[Q_a,\mathcal O(y)]\rangle$. The right side gives $-i\langle\delta_a\mathcal O(y)\rangle$. Since the surrounding insertions were arbitrary, the operator relation is

$$
[Q_a,\mathcal O(y)]=-i\delta_a\mathcal O(y).
$$

</details>

### Exercise 2: Check the background field strength

With $D=d-iA$, show that $D^2=-iF$ gives

$$
F=dA-iA\wedge A.
$$

<details>
<summary><strong>Solution</strong></summary>

Act on a field $\Phi$ in a representation of the symmetry group:

$$
D^2\Phi=(d-iA)(d\Phi-iA\Phi).
$$

Using the graded Leibniz rule, $d(A\Phi)=dA\,\Phi-A\wedge d\Phi$, so

$$
D^2\Phi=-i(dA)\Phi-A\wedge A\,\Phi
=-i(dA-iA\wedge A)\Phi.
$$

Therefore $D^2=-iF$ with $F=dA-iA\wedge A$.

</details>

### Exercise 3: Dimension of a higher-form symmetry operator

In $d$ dimensions, a $p$-form symmetry has topological operators supported on closed manifolds of dimension $d-p-1$. What is the support dimension for the symmetry operators of an ordinary symmetry, a one-form symmetry in four dimensions, and a two-form symmetry in six dimensions?

<details>
<summary><strong>Solution</strong></summary>

Use $d-p-1$.

For an ordinary symmetry, $p=0$, so the operator is supported on a codimension-one manifold of dimension $d-1$. In canonical quantization this is the spatial slice carrying the charge.

For a one-form symmetry in $d=4$, the topological operator is supported on a two-dimensional closed surface.

For a two-form symmetry in $d=6$, the topological operator is supported on a three-dimensional closed manifold.

</details>

### Exercise 4: Compare two anomaly conventions

Suppose another source defines $\delta_\lambda W[A]=-\int\lambda^a\mathcal A_a^{\mathrm{other}}[A]$. Relate $\mathcal A_a^{\mathrm{other}}$ to the anomaly functional $\mathcal A_a$ used on this page.

<details>
<summary><strong>Solution</strong></summary>

This page uses

$$
\delta_\lambda W[A]=\int\lambda^a\mathcal A_a[A].
$$

Equating the two expressions gives

$$
\mathcal A_a^{\mathrm{other}}=-\mathcal A_a.
$$

The two conventions describe the same anomalous variation of $W[A]$; only the name assigned to the local anomaly density differs.

</details>

## References

### Standard first pass

- Sidney Coleman, *Aspects of Symmetry*. Useful for currents, Ward identities, spontaneous symmetry breaking, solitons, instantons, and large-$N$ viewpoints.
- Mark Srednicki, *Quantum Field Theory*. Useful for continuous symmetries, discrete symmetries, non-Abelian symmetries, BRST symmetry, anomalies, and theta vacua.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for Noether’s theorem, Ward–Takahashi identities, gauge symmetry, spontaneous symmetry breaking, and anomaly calculations.
- A. Zee, *Quantum Field Theory in a Nutshell*. Useful for intuition about anomalies, monopoles, Chern–Simons terms, and topological QFT.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Useful for symmetry in quantum theory, antiunitary transformations, gauge theory, BRST, and anomalies.
- Luis Álvarez-Gaumé and Edward Witten, “Gravitational Anomalies.” Standard source for anomaly polynomials and descent in gravitational and mixed anomalies.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Standard source for higher-form global symmetry conventions.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for compact gauge fields, instantons, topology of gauge configurations, and loop operators.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*. Useful for topological terms, Wess–Zumino terms, Chern–Simons terms, anomalies, and gauge theory in matter systems.

## Version history

- **2026-06-16:** Initial polished conventions page for the volume.
