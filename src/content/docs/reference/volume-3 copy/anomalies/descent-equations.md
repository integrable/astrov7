---
title: "Descent Equations"
description: "Derives the Stora–Zumino descent equations from anomaly polynomials and explains how they produce consistent anomalies, counterterm ambiguities, and inflow actions."
sidebar:
  label: "Descent Equations"
  order: 14
level: Advanced
status: "Polished draft"
source: "Stora–Zumino descent; Wess–Zumino consistency; Chern–Weil theory; Bardeen–Zumino currents; Harvey TASI anomaly lectures; Alvarez-Gaumé–Witten; Bertlmann; Srednicki, Schwartz, and Weinberg."
topics:
  - descent equations
  - anomaly polynomial
  - Chern–Simons form
  - consistent anomaly
  - Wess–Zumino consistency
  - anomaly inflow
  - local counterterms
canonicalTopics:
  - descent-equations
  - anomaly-polynomial
  - consistent-anomaly
  - chern-simons-descent
  - anomaly-inflow
researchStatus:
  established:
    - "For local perturbative anomalies, the Stora–Zumino descent equations turn a closed invariant anomaly polynomial into a local consistent anomaly representative."
    - "Different descent representatives related by local counterterms describe the same anomaly class."
  active:
    - "Modern treatments extend the descent-and-inflow viewpoint using differential cohomology, eta invariants, invertible field theories, cobordism, and symmetry TFT."
---

## Summary

The **descent equations** are the mechanism by which a closed anomaly polynomial becomes an anomalous Ward identity.

For a $d$-dimensional QFT with local perturbative anomaly polynomial $I_{d+2}$, descent means choosing local forms

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

The final form $I_d^{(1)}$ is the local consistent anomaly representative. With the normalization used in this volume,

$$
\delta\log Z=2\pi i\int_{M_d} I_d^{(1)}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![The descent ladder from a closed anomaly polynomial to a Chern–Simons descendant, a consistent boundary anomaly, Wess–Zumino consistency, and the inflow interpretation.](/figures/symmetry-anomalies-topology/descent-equations-ladder.svg)

<figcaption>

Descent is the local algebraic bridge from the invariant polynomial $I_{d+2}$ to the anomalous variation on $M_d$. The same intermediate form $I_{d+1}^{(0)}$ also gives the inflow action on a bulk $X_{d+1}$ with $\partial X_{d+1}=M_d$.

</figcaption>
</figure>

The superscripts are bookkeeping: $I_{d+1}^{(0)}$ has form degree $d+1$ and ghost number zero, while $I_d^{(1)}$ has form degree $d$ and ghost number one. In ordinary infinitesimal language, ghost number one simply means that the expression is linear in the transformation parameter.

## Prerequisites

Read [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), and [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) first.

You should know the background-field convention

$$
D=d-iA,
\qquad
F=dA-iA\wedge A,
$$

and the effective-action normalization

$$
\delta\log Z=2\pi i\int_{M_d}I_d^{(1)}.
$$

Wedge products are usually suppressed: $A^3=A\wedge A\wedge A$ and $F^2=F\wedge F$.

## Core idea

An anomaly polynomial is a closed invariant form one degree too high to live directly as a density on $M_d$:

$$
I_{d+2}(F,R).
$$

Because it is closed, it can locally be written as the exterior derivative of a Chern–Simons-like form:

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

Because $I_{d+2}$ is invariant but $I_{d+1}^{(0)}$ is not, the variation of $I_{d+1}^{(0)}$ is closed. Locally it is exact:

$$
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

The resulting $I_d^{(1)}$ is the anomaly. More precisely, it is a **consistent** anomaly representative: it obeys Wess–Zumino consistency because it came from the variation of a local Chern–Simons descendant.

A compact slogan is

$$
\text{closed invariant polynomial}
\longrightarrow
\text{Chern–Simons descendant}
\longrightarrow
\text{consistent anomaly}.
$$

Descent explains why anomaly formulas often look like total derivatives in one higher dimension, why Chern–Simons terms appear in anomaly inflow, and why local counterterms can move anomaly terms around without changing the anomaly class.

## Setup and conventions

Let $M_d$ be a closed spacetime manifold unless boundaries are explicitly mentioned. Let $A$ denote an internal background gauge field, and let $R$ denote the curvature two-form of a background metric or spin connection.

A local perturbative anomaly polynomial is a closed invariant $(d+2)$-form

$$
dI_{d+2}=0,
\qquad
\delta I_{d+2}=0.
$$

For example, in $d=4$, a pure abelian cubic anomaly may be encoded by

$$
I_6=\frac{k}{6(2\pi)^3}F\wedge F\wedge F.
$$

Here $k=\sum_i q_i^3$ for left-handed Weyl fermions of charges $q_i$, with the opposite sign for opposite chirality. This is a local perturbative anomaly coefficient; it does not include possible global anomalies invisible to the polynomial.

:::note[Convention-sensitive source note]
Many references use anti-Hermitian connections, often denoted $\mathcal A$, and write characteristic classes with explicit factors of $i$. This volume uses Hermitian gauge fields and $F=dA-iA\wedge A$. When comparing Chern–Simons forms, translate the connection convention before comparing signs or powers of $i$.
:::

For an infinitesimal background gauge transformation, this volume writes

$$
\delta_\alpha A=D\alpha,
\qquad
\delta_\alpha F=i[\alpha,F],
$$

with the sign of the bracket fixed by this convention. If a source uses $\delta A=-D\alpha$, its descendant $I_d^{(1)}$ differs by a corresponding sign.

## Chern–Weil transgression

The first descent step is a standard Chern–Weil fact. An invariant polynomial in the curvature is closed, and locally it is the exterior derivative of a Chern–Simons form.

For an invariant polynomial $P(F)$ of degree $n+1$,

$$
P(F)=\operatorname{Tr}(F^{n+1}),
$$

one convenient descendant is obtained by interpolating from the zero connection to $A$:

$$
A_t=tA,
\qquad
F_t=dA_t-iA_t\wedge A_t.
$$

Then

$$
Q_{2n+1}(A)
=(n+1)\int_0^1dt\,\operatorname{Tr}\!\left(A\wedge F_t^n\right)
$$

satisfies, up to the overall normalization chosen for $P$,

$$
dQ_{2n+1}(A)=\operatorname{Tr}(F^{n+1}).
$$

The form $Q_{2n+1}$ is the Chern–Simons descendant. In anomaly notation it is the local form $I_{d+1}^{(0)}$ when $2n+2=d+2$.

The exact polynomial expression depends on conventions and integrations by parts. For example, in an anti-Hermitian convention one often writes

$$
Q_3=\operatorname{Tr}\!\left(\mathcal A\,d\mathcal A+\frac{2}{3}\mathcal A^3\right).
$$

In the Hermitian convention used here the same expression is obtained after setting $\mathcal A=-iA$ and translating the trace normalization. This is one reason anomaly pages should state conventions before quoting Chern–Simons formulas.

## The BRST descent tower

The most compact version of descent uses the BRST differential $s$. Replace the infinitesimal parameter by a Grassmann-odd ghost $c$. Schematically,

$$
sA=Dc,
\qquad
sF=i[c,F],
$$

with the ghost self-transformation chosen so that $s^2=0$.

The local descent equations are

$$
I_{d+2}^{(0)}=dI_{d+1}^{(0)},
$$

$$
sI_{d+1}^{(0)}+dI_d^{(1)}=0,
$$

$$
sI_d^{(1)}+dI_{d-1}^{(2)}=0,
$$

and so on. The total degree

$$
\text{form degree}+\text{ghost number}
$$

stays fixed along the tower.

The second line is the anomaly statement. The third line is the Wess–Zumino consistency condition in local cohomological form. It says that the anomaly is BRST closed up to a total derivative:

$$
sI_d^{(1)}=-dI_{d-1}^{(2)}.
$$

On a closed $M_d$,

$$
s\int_{M_d}I_d^{(1)}=0.
$$

Thus a consistent anomaly is a BRST cocycle.

It is also defined only modulo BRST-exact and total-derivative shifts. A local counterterm $L_d^{(0)}$ shifts

$$
\log Z\longrightarrow \log Z+2\pi i\int_{M_d}L_d^{(0)},
$$

so the anomaly changes by

$$
I_d^{(1)}\longrightarrow I_d^{(1)}+sL_d^{(0)}+dL_{d-1}^{(1)}.
$$

This is why the local expression for the anomaly is not unique, while its cohomology class is meaningful.

## A four-dimensional abelian example

Take a four-dimensional theory with a $U(1)$ background field and anomaly polynomial

$$
I_6=\frac{k}{6(2\pi)^3}F^3.
$$

Since $F=dA$ in the abelian case,

$$
I_6=d\left[\frac{k}{6(2\pi)^3}A\wedge F\wedge F\right].
$$

Thus

$$
I_5^{(0)}=\frac{k}{6(2\pi)^3}A\wedge F\wedge F.
$$

Under a background gauge transformation $\delta_\alpha A=d\alpha$,

$$
\delta_\alpha I_5^{(0)}
=\frac{k}{6(2\pi)^3}d\alpha\wedge F\wedge F
=d\left[\frac{k}{6(2\pi)^3}\alpha F\wedge F\right].
$$

Therefore

$$
I_4^{(1)}(\alpha,A)=\frac{k}{6(2\pi)^3}\alpha F\wedge F.
$$

The anomalous variation is

$$
\delta_\alpha\log Z[A]
=2\pi i\int_{M_4}I_4^{(1)}
=\frac{ik}{24\pi^2}\int_{M_4}\alpha F\wedge F.
$$

This is the consistent $U(1)^3$ anomaly in the normalization of this page.

In components,

$$
F\wedge F
=\frac{1}{4}\epsilon^{\mu\nu\rho\sigma}
F_{\mu\nu}F_{\rho\sigma}\,d^4x.
$$

Therefore

$$
\delta_\alpha\log Z[A]
=\frac{ik}{96\pi^2}\int d^4x\,
\alpha\,\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}.
$$

Whether a textbook writes a coefficient as $1/(96\pi^2)$, $1/(48\pi^2)$, or $1/(24\pi^2)$ often depends on whether it is quoting the effective-action variation, the current divergence, one Weyl current, one Dirac axial current, or a convention where $F\widetilde F$ already contains a factor of $1/2$.

:::caution[Coefficient trap]
Do not compare anomaly coefficients before checking four choices: one Weyl fermion versus one Dirac axial current, consistent versus covariant current, $F\wedge F$ versus $F_{\mu\nu}\widetilde F^{\mu\nu}$, and Hermitian versus anti-Hermitian gauge fields.
:::

## Nonabelian descent and the consistent anomaly

For a nonabelian background field, the same idea works but the Chern–Simons form contains nonlinear powers of $A$.

For a four-dimensional gauge anomaly with polynomial proportional to

$$
I_6\propto \operatorname{Tr}(F^3),
$$

the Chern–Simons descendant is proportional to

$$
Q_5(A)=3\int_0^1dt\,\operatorname{Tr}\left(A\wedge F_t\wedge F_t\right).
$$

The gauge variation of $Q_5(A)$ gives a four-form $Q_4^{(1)}(\alpha,A)$. Its explicit expression is longer than the abelian formula, but its role is the same:

$$
\delta_\alpha Q_5(A)=dQ_4^{(1)}(\alpha,A),
$$

and

$$
\delta_\alpha\log Z[A]\propto \int_{M_4}Q_4^{(1)}(\alpha,A).
$$

This $Q_4^{(1)}$ is the **consistent** anomaly. It satisfies Wess–Zumino consistency but does not transform covariantly as a tensor under the gauge group. The covariant anomaly is obtained by adding the Bardeen–Zumino current. The two versions represent the same underlying anomaly class but answer different practical questions.

The nonabelian descent formula is also where group theory enters. In four dimensions, the anomaly involves the symmetric cubic invariant

$$
d^{abc}_R=\operatorname{tr}_R\!\left(T^a\{T^b,T^c\}\right),
$$

so perturbative nonabelian gauge anomalies vanish for representations with zero cubic invariant.

## Counterterms and ambiguity of representatives

Descent representatives are not unique. Suppose

$$
I_{d+1}^{(0)}\longrightarrow I_{d+1}^{(0)}+dL_d^{(0)}.
$$

Then

$$
\delta I_{d+1}^{(0)}\longrightarrow
\delta I_{d+1}^{(0)}+d(\delta L_d^{(0)}),
$$

so

$$
I_d^{(1)}\longrightarrow I_d^{(1)}+\delta L_d^{(0)}+dL_{d-1}^{(1)}.
$$

On a closed spacetime, the total derivative integrates to zero, while $\delta L_d^{(0)}$ is the variation of the local counterterm

$$
2\pi i\int_{M_d}L_d^{(0)}.
$$

Thus the local anomaly density changes, but the anomaly class does not.

This is the precise form of a common phrase: **local counterterms can move anomalies between currents, but they cannot remove a nontrivial anomaly class**.

A classic example is the Bardeen counterterm in theories with vector and axial backgrounds. One may choose a scheme that preserves the vector current and places the anomaly in the axial current. That choice is not magic; it is a choice of representative in the descent class compatible with the physical requirement that the vector symmetry be gaugeable.

## Inflow from the descendant

Let $M_d=\partial X_{d+1}$. Define the inflow functional

$$
S_{\rm inflow}[A]=2\pi i\int_{X_{d+1}}I_{d+1}^{(0)}.
$$

Its variation is

$$
\delta S_{\rm inflow}
=2\pi i\int_{X_{d+1}}dI_d^{(1)}
=2\pi i\int_{M_d}I_d^{(1)}.
$$

If a $d$-dimensional boundary theory has the opposite anomalous variation, the combined bulk-plus-boundary system is invariant.

This is anomaly inflow. The descent equations are the local perturbative version of the more general statement that an anomalous $d$-dimensional theory can often be viewed as living on the boundary of a one-higher-dimensional invertible theory.

The local Chern–Simons expression is not always globally well-defined as an ordinary integral over one coordinate patch. Globally, the inflow action is better understood through differential characters, eta invariants, or invertible field theory data. The local descent equations are the coordinate chart of that richer object.

## Gravitational descent

For gravitational anomalies, replace the gauge connection by the spin connection $\omega$ and the gauge curvature by the curvature two-form $R^a{}_b$.

For example, a two-dimensional pure gravitational anomaly is associated with a four-form proportional to

$$
p_1(T)=-\frac{1}{8\pi^2}\operatorname{tr}R\wedge R.
$$

Locally,

$$
\operatorname{tr}R\wedge R=dQ_3^{(0)}(\omega),
$$

where, in a standard anti-Hermitian spin-connection convention,

$$
Q_3^{(0)}(\omega)=\operatorname{tr}\left(\omega\wedge d\omega+\frac{2}{3}\omega^3\right).
$$

A local Lorentz variation of $Q_3^{(0)}$ produces a two-dimensional gravitational anomaly descendant. Diffeomorphism anomalies can be treated similarly, though the bookkeeping is more subtle because diffeomorphisms act on both fields and coordinates.

The slogan remains the same:

$$
\text{curvature polynomial}
\longrightarrow
\text{gravitational Chern–Simons form}
\longrightarrow
\text{gravitational anomaly}.
$$

## Descent versus anomaly matching

Descent computes a local representative of an anomaly. Anomaly matching uses the resulting anomaly class as RG-invariant data.

If the UV theory has anomaly polynomial $I_{d+2}^{\rm UV}$ for a global symmetry $G$, then any IR description preserving $G$ must reproduce the same anomaly class:

$$
I_{d+2}^{\rm IR}=I_{d+2}^{\rm UV}
$$

up to counterterm-equivalent representatives and contributions from decoupled topological sectors.

This equality is not a dynamical equation of motion. It is a consistency condition on possible long-distance theories. The next chapter develops this viewpoint systematically.

## What descent does not capture

Descent from a differential-form anomaly polynomial captures **local perturbative** anomalies. It does not capture every anomaly.

Important anomalies can be invisible to the local polynomial, including:

- global anomalies detected by large gauge transformations;
- torsion anomalies of finite symmetries;
- some fermionic anomalies depending on spin or Pin structure;
- anomalies of non-invertible symmetries whose algebra is not group-like;
- subtleties involving boundaries, defects, and nontrivial background topology.

This limitation is not a flaw of descent. Descent is doing exactly what it was built to do: classify local infinitesimal anomalies. The modern language of invertible field theories and symmetry TFT extends the same inflow logic beyond the local perturbative regime.

## Common pitfalls

**Treating $I_{d+2}$ as the anomaly density.**  The anomaly density on $M_d$ is $I_d^{(1)}$, not $I_{d+2}$. The polynomial generates the anomaly by descent.

**Forgetting the counterterm ambiguity.**  A different descent representative can change the local current divergence. The invariant datum is the cohomology class, not every term in a particular formula.

**Confusing consistent and covariant anomalies.**  Descent naturally gives the consistent anomaly. The covariant anomaly is obtained after adding the Bardeen–Zumino current.

**Ignoring global issues.**  The form $I_{d+1}^{(0)}$ is local. On topologically nontrivial backgrounds, a globally correct inflow action may need more refined data.

**Comparing coefficients too quickly.**  Factors of $2$, $2\pi$, $i$, and $1/2$ in $\widetilde F^{\mu\nu}$ are convention traps. Convert all conventions before declaring disagreement.

## Relations to other pages

- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) explains the characteristic-class object from which descent starts.
- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) explains why the descent anomaly is consistent.
- [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/) explains why the descent current is not usually the covariant current.
- [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) explains anomalies that are not detected by local descent.
- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) uses the same equations from the one-higher-dimensional viewpoint.

## Research status

The local descent formalism is settled and standard. It is one of the cleanest bridges among triangle diagrams, Fujikawa Jacobians, BRST cohomology, Chern–Simons terms, index theory, and anomaly inflow.

Active work lies mostly beyond the local perturbative setting: torsion anomalies, fermionic phases, discrete symmetries, higher-form symmetries, non-invertible symmetries, differential-cohomology refinements, and the symmetry-TFT packaging of anomaly data.

## Exercises

### Exercise 1: Abelian descent in two dimensions

Let

$$
I_4=\frac{k}{2(2\pi)^2}F\wedge F
$$

for a two-dimensional theory with $U(1)$ background field $A$. Find $I_3^{(0)}$, $I_2^{(1)}$, and $\delta_\alpha\log Z$.

<details><summary><strong>Solution</strong></summary>

Because $F=dA$,

$$
I_4=d\left[\frac{k}{2(2\pi)^2}A\wedge F\right].
$$

Thus

$$
I_3^{(0)}=\frac{k}{2(2\pi)^2}A\wedge F.
$$

Under $\delta_\alpha A=d\alpha$,

$$
\delta_\alpha I_3^{(0)}
=\frac{k}{2(2\pi)^2}d\alpha\wedge F
=d\left[\frac{k}{2(2\pi)^2}\alpha F\right].
$$

So

$$
I_2^{(1)}=\frac{k}{2(2\pi)^2}\alpha F.
$$

The anomalous variation is

$$
\delta_\alpha\log Z
=2\pi i\int_{M_2}I_2^{(1)}
=\frac{ik}{4\pi}\int_{M_2}\alpha F.
$$

</details>

### Exercise 2: Counterterm shift

Suppose a descent representative changes by

$$
I_{d+1}^{(0)}\to I_{d+1}^{(0)}+dL_d^{(0)}.
$$

Show that the integrated anomaly changes by the variation of a local counterterm on a closed spacetime.

<details><summary><strong>Solution</strong></summary>

The variation changes as

$$
\delta I_{d+1}^{(0)}\to \delta I_{d+1}^{(0)}+d(\delta L_d^{(0)}).
$$

Therefore

$$
I_d^{(1)}\to I_d^{(1)}+\delta L_d^{(0)}+dL_{d-1}^{(1)}
$$

for some local $(d-1)$-form $L_{d-1}^{(1)}$. On a closed spacetime,

$$
\int_{M_d}dL_{d-1}^{(1)}=0.
$$

The integrated anomaly changes by

$$
2\pi i\int_{M_d}\delta L_d^{(0)}
=\delta\left(2\pi i\int_{M_d}L_d^{(0)}\right),
$$

which is the variation of a local counterterm.

</details>

### Exercise 3: Why descent gives Wess–Zumino consistency

Use

$$
sI_{d+1}^{(0)}+dI_d^{(1)}=0
$$

and $s^2=0$ to show that the integrated anomaly is BRST closed on a closed spacetime.

<details><summary><strong>Solution</strong></summary>

Apply $s$:

$$
0=s^2I_{d+1}^{(0)}=-s(dI_d^{(1)}).
$$

Since $s$ anticommutes with $d$ in the total graded complex,

$$
d(sI_d^{(1)})=0.
$$

Locally this means

$$
sI_d^{(1)}+dI_{d-1}^{(2)}=0.
$$

Integrating over closed $M_d$ gives

$$
s\int_{M_d}I_d^{(1)}=-\int_{M_d}dI_{d-1}^{(2)}=0.
$$

This is the BRST form of Wess–Zumino consistency.

</details>

## References

- R. Stora, early lectures on algebraic structure of anomalies and descent.
- B. Zumino, Y.-S. Wu, and A. Zee, **Chiral Anomalies, Higher Dimensions, and Differential Geometry**, *Nuclear Physics B* 239 (1984).
- L. Alvarez-Gaumé and E. Witten, **Gravitational Anomalies**, *Nuclear Physics B* 234 (1984).
- W. A. Bardeen and B. Zumino, **Consistent and Covariant Anomalies in Gauge and Gravitational Theories**, *Nuclear Physics B* 244 (1984).
- J. A. Harvey, **TASI 2003 Lectures on Anomalies**, arXiv:hep-th/0509097.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*.
- M. Srednicki, *Quantum Field Theory*, §§75–77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, Chapters 15–17.

## Version history

- 2026-06-18: First polished draft. Added descent derivation, abelian example, nonabelian transgression formula, counterterm ambiguity, inflow interpretation, gravitational descent, pitfalls, and exercises.
