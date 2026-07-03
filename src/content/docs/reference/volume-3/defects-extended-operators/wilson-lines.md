---
title: "Wilson Lines"
description: "Wilson lines and Wilson loops as gauge holonomy operators, representation-labeled extended observables, confinement diagnostics, and charged objects for one-form symmetry."
sidebar:
  label: "Wilson Lines"
  order: 2
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Ch. 7; Srednicki §82; Schwartz Ch. 25; Gaiotto–Kapustin–Seiberg–Willett; standard gauge-theory and Chern–Simons references."
topics:
  - Wilson lines
  - Wilson loops
  - gauge holonomy
  - line operators
  - gauge invariance
  - confinement
  - center symmetry
  - one-form symmetry
canonicalTopics:
  - wilson-line
  - wilson-loop
  - gauge-holonomy
  - line-operator
  - center-one-form-symmetry
researchStatus:
  established:
    - "Wilson lines are standard representation-labeled gauge-holonomy operators and are among the central observables of gauge theory."
    - "Large Wilson loops diagnose static potentials, screening, and confinement patterns, subject to matter-content and renormalization caveats."
  active:
    - "Wilson-line algebras, line-defect RG, generalized symmetries, global-form dependence, and line operators in strongly coupled QFT remain active research tools."
---

## Summary

A Wilson line is the quantum operator associated with parallel transport of a gauge charge along a curve. If $A$ is a gauge connection and $C$ is an oriented path, the basic object is

$$
U_R(C)=P\exp\!\left(i\int_C A_R\right),
$$

where $R$ is a representation and $P$ means path ordering. For a closed curve, the trace gives a gauge-invariant Wilson loop,

$$
W_R(C)=\operatorname{Tr}_R P\exp\!\left(i\oint_C A_R\right).
$$

Wilson lines are the first essential extended operators in gauge theory. They are not merely useful observables; they test the global form of the gauge group, encode the response of heavy charged probes, diagnose confinement and screening, and furnish the basic charged objects for one-form symmetries.

<figure class="doc-figure" style="--figure-width: 62rem;">

![Wilson-line diagram showing open parallel transport, closed Wilson loops, center one-form symmetry linking, rectangular Wilson-loop static-potential diagnostics, and operator-data caveats.](/figures/symmetry-anomalies-topology/wilson-line-holonomy-diagnostics.svg)

<figcaption>

A Wilson line is a holonomy operator. An open Wilson line transforms at its endpoints; a closed traced Wilson loop is gauge invariant. Large rectangular Wilson loops diagnose static potentials, while linking by a one-form symmetry operator detects center charge.

</figcaption>
</figure>

## Prerequisites

You should know the distinction between [global symmetry and gauge redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), the background-field idea from [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), and the taxonomy from [Local Versus Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/local-versus-extended-operators/). It also helps to know connections, covariant derivatives, representation theory, and the center of a compact Lie group.

## Setup and conventions

We use the volume convention

$$
D=d-iA,
$$

where $A=A^aT^a$ is a Hermitian-matrix-valued one-form in the relevant representation. A matter field in representation $R$ transforms as

$$
\psi(x)\mapsto g(x)\psi(x),
$$

and the gauge field transforms as

$$
A\mapsto A^g=gAg^{-1}+ig\,dg^{-1}.
$$

For a path $C:[0,1]\to M_d$, define

$$
A_t(t)=\dot x^\mu(t)A_\mu(x(t)).
$$

The parallel transporter in representation $R$ is

$$
U_R(C)=P\exp\!\left(i\int_0^1 dt\,A_{R,t}(t)\right).
$$

It solves

$$
\frac{d}{dt}U_R(t,0)=iA_{R,t}(t)U_R(t,0),
\qquad
U_R(0,0)=1.
$$

:::note[Convention-sensitive source note]
Many books use anti-Hermitian generators or the covariant derivative $D=d+A$. With Hermitian generators and $D=d-iA$, the Wilson line is $P\exp(i\int A_R)$. Switching conventions moves signs between $D$, the gauge transformation of $A$, and the exponential. The gauge-transformation law below is the safest way to check the convention.
:::

## Gauge transformation of an open line

Let $C$ run from $x_i$ to $x_f$. The parallel transporter transforms as

$$
U_R(C_{x_i\to x_f})
\mapsto
R(g(x_f))\,U_R(C_{x_i\to x_f})\,R(g(x_i))^{-1}.
$$

This is the key fact. It says that an open Wilson line is not gauge invariant by itself. It carries gauge indices at its endpoints.

There are three common ways to make sense of an open Wilson line:

1. Attach charged endpoint operators:

$$
\bar\psi(x_f)\,U_R(C_{x_i\to x_f})\,\psi(x_i).
$$

2. Let the line end on a boundary condition or defect that can absorb the charge.

3. Work with a background gauge field for a global symmetry, where the line may represent a parallel-transport factor in a charged correlator rather than a dynamical gauge-invariant observable.

The closed Wilson loop avoids endpoint transformations by taking a trace:

$$
W_R(C)=\operatorname{Tr}_R U_R(C),
\qquad \partial C=\varnothing.
$$

Some authors normalize by $\dim R$ and define

$$
\widetilde W_R(C)=\frac{1}{\dim R}\operatorname{Tr}_R U_R(C).
$$

Both are common. This page uses the unnormalized trace unless explicitly stated.

## The abelian case

For compact $U(1)$ gauge theory, a charge-$q$ Wilson line is

$$
W_q(C)=\exp\!\left(iq\int_C A\right).
$$

For a closed curve, under a small gauge transformation $A\mapsto A+d\lambda$,

$$
\oint_C A\mapsto \oint_C A+\oint_C d\lambda=\oint_C A.
$$

Large gauge transformations impose charge quantization. If $A$ is normalized so that a minimally charged field has charge $1$, then allowed Wilson charges are usually $q\in\mathbb Z$. More generally, the allowed charges form the character lattice of the compact gauge group.

For an open path,

$$
\exp\!\left(iq\int_{x_i}^{x_f} A\right)
\mapsto
\exp\!\left(iq\lambda(x_f)\right)
\exp\!\left(iq\int_{x_i}^{x_f} A\right)
\exp\!\left(-iq\lambda(x_i)\right).
$$

The endpoint phases must be canceled by endpoint charged fields.

## The nonabelian case and path ordering

For a nonabelian gauge group, matrices $A_t(t_1)$ and $A_t(t_2)$ need not commute. The exponential must be path ordered:

$$
P\exp\!\left(i\int_0^1dt\,A_t(t)\right)
=1+i\int_0^1dt_1\,A_t(t_1)
+i^2\int_{0<t_2<t_1<1}dt_1dt_2\,A_t(t_1)A_t(t_2)+\cdots.
$$

Path ordering is not a technical nuisance; it is what makes the line compute nonabelian parallel transport. Reversing the orientation of the path gives the inverse transporter,

$$
U_R(C^{-1})=U_R(C)^{-1},
$$

for a unitary representation and a sufficiently regular connection.

For a small closed loop bounding an infinitesimal surface element $\delta\Sigma^{\mu\nu}$, the Wilson loop measures curvature:

$$
U(C_{\rm small})=1+iF_{\mu\nu}\delta\Sigma^{\mu\nu}+O(\delta\Sigma^{3/2}),
$$

up to orientation conventions. This is the local reason Wilson loops are sensitive to field strength, while the full finite loop is sensitive to global holonomy.

## Representation labels and global form

The Wilson loop label $R$ must be a representation of the actual gauge group, not merely a representation of the Lie algebra.

For example, $SU(2)$ and $SO(3)=SU(2)/\mathbb Z_2$ have the same Lie algebra $\mathfrak{su}(2)$ but different allowed Wilson lines. Half-integer spin representations are honest representations of $SU(2)$, but not of $SO(3)$. Thus the spin-$1/2$ Wilson loop is allowed in an $SU(2)$ gauge theory but not as a genuine Wilson loop in an $SO(3)$ gauge theory.

This matters physically. The set of allowed Wilson lines helps define the global form of the theory. In four-dimensional Yang–Mills theory, the full line-operator spectrum depends on the global form of the gauge group and on which electric and magnetic lines are mutually local.

:::note[Global-form warning]
A Lagrangian written with Lie-algebra-valued gauge fields does not by itself determine all Wilson lines. The global form of the gauge group, matter representations, spin structure, and allowed magnetic sectors can change the line-operator spectrum while leaving the local gauge algebra unchanged.
:::

## Wilson lines as heavy probe particles

A Wilson line can be derived by integrating out a very heavy charged particle whose worldline is fixed to be $C$. A heavy particle of charge $q$ coupled to a gauge field contributes the phase

$$
\exp\!\left(iq\int_C A\right)
$$

in the abelian case. In the nonabelian case, the internal color state is parallel transported, producing $U_R(C)$.

This gives the physical interpretation:

> A Wilson line inserts an infinitely heavy external probe carrying gauge charge in representation $R$.

The word “external” matters. A Wilson line need not correspond to a dynamical particle in the spectrum. It can be a probe used to diagnose the vacuum.

## Rectangular Wilson loops and static potentials

Consider a rectangular Wilson loop with time extent $T$ and spatial separation $L$. In a confining or screening theory, the large-$T$ behavior often has the form

$$
\langle W_R(T,L)\rangle\sim e^{-T V_R(L)},
\qquad T\gg L,
$$

where $V_R(L)$ is the static potential between an external probe and antiprobe in representation $R$.

If

$$
V_R(L)\sim \sigma_R L
$$

at large $L$, then

$$
\langle W_R(T,L)\rangle\sim e^{-\sigma_R TL}.
$$

This is the famous **area law**. It indicates a flux tube with tension $\sigma_R$ and is a confinement diagnostic.

If instead the loop behaves like

$$
\langle W_R(C)\rangle\sim e^{-\mu\operatorname{Perimeter}(C)},
$$

then the Wilson loop has a **perimeter law**, often associated with screening, Higgs behavior, or deconfinement depending on the theory and dimension.

A useful slogan is:

$$
\text{area law}\leftrightarrow \text{linear potential for external probes},
$$

but the slogan has caveats. Dynamical matter in representation $R$ can screen the probe charge and break the string. Then asymptotic area law for that representation can be lost even if the theory still confines in a broader sense.

## Center charge and one-form symmetry

In a pure gauge theory with gauge group $SU(N)$ and no dynamical fundamental matter, Wilson lines are charged under the center $\mathbb Z_N$. The relevant symmetry is a one-form symmetry: it acts on line operators rather than local operators.

If $z\in \mathbb Z_N$ and $R$ has $N$-ality $q_R$, then the one-form symmetry action is

$$
W_R(C)\mapsto z^{q_R}W_R(C).
$$

Geometrically, the symmetry operator is supported on a codimension-two surface $M_{d-2}$. It acts when $M_{d-2}$ links the Wilson line $C$:

$$
U_z(M_{d-2})\,W_R(C)=z^{q_R\operatorname{Link}(M_{d-2},C)}W_R(C).
$$

This is one of the cleanest examples of the general rule: a $q$-form symmetry acts on $q$-dimensional charged operators by linking.

Dynamical matter in the fundamental representation explicitly breaks the center one-form symmetry, because fundamental Wilson lines can end on dynamical matter fields. In that case, the line is no longer absolutely conserved as a charged object.

## Wilson lines in background fields

Wilson lines also appear when $A$ is a background gauge field for a global symmetry. Suppose local operators $\mathcal O_i(x_i)$ transform in representations $R_i$ of a global symmetry group $G$. Coupling to a background $G$ connection lets us compare charged data at different points by parallel transport.

In that case, Wilson lines are not summed over in the path integral; they are built from external sources. They organize covariance of correlation functions under background gauge transformations. This is conceptually different from a dynamical Wilson line in a gauge theory, but the same holonomy formula appears.

This is why Wilson-line notation shows up in both gauge theory and global-symmetry background-field discussions.

## Wilson lines versus charged local fields

In a dynamical gauge theory, a bare charged field $\psi(x)$ is gauge variant and is not an observable. A gauge-invariant charged excitation must be dressed. A simple formal dressing from $x$ to a reference point or boundary is

$$
\Psi(x;C)=U(C_{x\to \infty})\psi(x),
$$

with appropriate indices suppressed. Whether this is a good physical operator depends on boundary conditions, infrared behavior, and gauge choice. In QED, charged particles require long-range electromagnetic dressing; in nonabelian confining theories, isolated color charges do not appear as finite-energy asymptotic states.

This is the operator-level reason gauge theory is subtle: charged fields in a Lagrangian are not automatically gauge-invariant local observables.

## Wilson lines in Chern–Simons theory

In three-dimensional Chern–Simons theory, Wilson loops are especially powerful. The action is topological, and Wilson-loop expectation values can produce knot and link invariants. However, one must choose a framing: a way to slightly thicken or displace the loop so that self-linking is well-defined.

This gives an important lesson that persists beyond Chern–Simons theory:

> A line operator may require extra geometric data, such as framing, even when the classical formula looks complete.

In ordinary Yang–Mills theory, Wilson lines also require renormalization. Long straight lines have linear divergences, cusped lines have cusp anomalous dimensions, and intersecting lines can mix under renormalization. In topological Chern–Simons theory, framing is the topological avatar of this UV sensitivity.

## Renormalization of Wilson lines

A Wilson line is a composite operator with UV divergences localized along its support. The simplest divergence is proportional to its length,

$$
W_R(C)_{\rm bare}\sim e^{-\delta m_R\operatorname{Length}(C)}W_R(C)_{\rm ren},
$$

in a cutoff scheme. Physically, this is the self-energy of the heavy external probe.

If the curve has a cusp with angle $\gamma$, there is an additional logarithmic divergence governed by the cusp anomalous dimension,

$$
W_{\rm cusp}\sim \exp\!\left[-\Gamma_{\rm cusp}(\gamma)\log(\Lambda/\mu)+\cdots\right].
$$

Cusp anomalous dimensions are central in modern perturbative gauge theory, infrared factorization, and scattering amplitudes. They are not the main topic of this volume, but the warning matters: Wilson lines are conceptually simple and technically rich.

## Screening and endpoints

A Wilson line can end if the theory contains dynamical matter with the appropriate charge. For example, in a gauge theory with a fundamental field $\psi$, an open fundamental Wilson line can be completed into

$$
\bar\psi(x_f)U(C_{x_i\to x_f})\psi(x_i).
$$

This means the corresponding one-form charge is not conserved: the line can break by pair creation of dynamical matter. In confinement language, a flux tube between external charges can snap if the vacuum can produce dynamical charges that screen the endpoints.

This is why one should never discuss “the Wilson-loop area law” without specifying the matter content and representation.

## Relation to ’t Hooft lines

Wilson lines are electric line operators. ’t Hooft lines are magnetic line operators. In four-dimensional gauge theory, one often labels a general line by electric and magnetic data,

$$
(e,m),
$$

subject to quantization and mutual-locality constraints. Wilson lines have $m=0$; ’t Hooft lines have $e=0$ in a chosen duality frame; dyonic Wilson–’t Hooft lines have both.

Electric-magnetic duality can exchange Wilson and ’t Hooft lines. This is one reason line operators are more invariant than Lagrangian variables: a duality may turn an order-type holonomy operator into a disorder-type magnetic operator.

The next page studies this magnetic counterpart.

## Common pitfalls

**Forgetting path ordering.** In a nonabelian theory, $P$ is essential. Without path ordering, the exponential does not transform correctly as parallel transport.

**Treating an open Wilson line as gauge invariant.** It is not gauge invariant unless its endpoints are attached to charged operators, boundaries, or other defects that absorb the endpoint transformations.

**Confusing the Lie algebra with the gauge group.** Wilson-line labels are representations of the actual gauge group. Theories with the same Lie algebra can have different Wilson lines.

**Ignoring normalization.** Some authors define $W_R$ with $\operatorname{Tr}_R$, others with $(\dim R)^{-1}\operatorname{Tr}_R$. This changes large-$N$ limits and comparisons of expectation values but not the underlying holonomy.

**Interpreting area law too naively.** Dynamical matter can screen charges. The representation matters. A theory can have confinement-like physics while some Wilson loops show perimeter behavior due to screening.

**Forgetting UV divergences.** Wilson lines are extended composite operators and need renormalization. Cusps, endpoints, and intersections carry extra local data.

**Calling every holonomy a Wilson loop.** A holonomy in a background connection is a useful parallel-transport factor, but a Wilson loop in a dynamical gauge theory is an operator integrated over gauge fields.

## Relation to nearby pages

This page is the electric line-operator entry point. [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) gives the magnetic disorder analogue. [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) treats higher-dimensional support. [Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/) studies mutual locality and electric/magnetic charge lattices.

Later, [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) and [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) use Wilson lines as charged objects for one-form symmetry. The gauge-theory volume uses Wilson loops as diagnostics of confinement, deconfinement, and lattice gauge theory.

## Research status

Wilson lines are completely standard, but their uses are still expanding. In perturbative gauge theory, Wilson lines organize soft and collinear factorization. In nonperturbative gauge theory, they diagnose confinement and center symmetry. In supersymmetric theories, special Wilson lines can be protected and exactly computable. In Chern–Simons theory, they produce knot invariants. In modern symmetry language, they are the canonical charged objects of one-form symmetries.

The basic formula is old. The operator-theoretic ecosystem around it is very much alive.

## Exercises

### Exercise 1: Gauge transformation of a Wilson line

Using the convention $D=d-iA$, show that the parallel transporter along $C:x_i\to x_f$ transforms as

$$
U_R(C)\mapsto R(g(x_f))U_R(C)R(g(x_i))^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

The parallel transporter satisfies

$$
\frac{d}{dt}U(t,0)=iA_t(t)U(t,0),\qquad U(0,0)=1.
$$

Under a gauge transformation,

$$
A\mapsto A^g=gAg^{-1}+ig\,dg^{-1}.
$$

Define

$$
U^g(t,0)=g(x(t))U(t,0)g(x(0))^{-1}.
$$

Then

$$
\frac{d}{dt}U^g(t,0)
=\left(\dot g g^{-1}+g iA_t g^{-1}\right)U^g(t,0).
$$

Using $\frac{d}{dt}g^{-1}=-g^{-1}\dot g g^{-1}$, the transformed connection along the path is

$$
A^g_t=gA_tg^{-1}+ig\frac{d}{dt}g^{-1}
=gA_tg^{-1}-i\dot g g^{-1}.
$$

Therefore

$$
iA^g_t=i gA_tg^{-1}+\dot g g^{-1},
$$

so $U^g(t,0)$ satisfies the transformed parallel-transport equation. At $t=1$ this gives

$$
U(C)\mapsto g(x_f)U(C)g(x_i)^{-1}.
$$

In representation $R$, insert $R(g)$ everywhere.

</details>

### Exercise 2: Gauge invariance of a closed Wilson loop

Use the previous result to show that $\operatorname{Tr}_R U_R(C)$ is gauge invariant when $C$ is closed.

<details><summary><strong>Solution</strong></summary>

For a closed curve, $x_f=x_i=x_0$. The transformation law becomes

$$
U_R(C)\mapsto R(g(x_0))U_R(C)R(g(x_0))^{-1}.
$$

Taking the trace gives

$$
\operatorname{Tr}_R\left(R(g)U_R(C)R(g)^{-1}\right)=\operatorname{Tr}_R U_R(C),
$$

by cyclicity of the trace. Hence the closed Wilson loop is gauge invariant.

</details>

### Exercise 3: Small-loop expansion

For a small rectangular loop in the $\mu\nu$ plane with area $\delta\Sigma^{\mu\nu}$, show schematically that the Wilson loop measures $F_{\mu\nu}$ to leading order.

<details><summary><strong>Solution</strong></summary>

For an infinitesimal loop, multiply the four short parallel transports around the rectangle and expand to second order in side lengths. The first-order terms cancel because the path closes. The surviving second-order term is the curvature of the connection,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu-i[A_\mu,A_\nu]
$$

in the convention $D=\partial-iA$. Thus

$$
U(C_{\rm small})=1+iF_{\mu\nu}\delta\Sigma^{\mu\nu}+\cdots,
$$

with the sign depending on the orientation of the loop and the convention for $F$. This is the infinitesimal relation between holonomy and curvature.

</details>

### Exercise 4: Static potential from a rectangular Wilson loop

Assume

$$
\langle W(T,L)\rangle\sim e^{-T V(L)}
$$

for $T\gg L$. If the Wilson loop has an area law $\langle W(T,L)\rangle\sim e^{-\sigma TL}$, what is $V(L)$?

<details><summary><strong>Solution</strong></summary>

Compare the exponents:

$$
-T V(L)=-\sigma TL.
$$

Therefore

$$
V(L)=\sigma L.
$$

The potential grows linearly with separation. This is the static-probe version of confinement.

</details>

### Exercise 5: Center charge of an $SU(N)$ Wilson line

Let $z=e^{2\pi i/N}$ generate the center of $SU(N)$. A representation $R$ has $N$-ality $q_R$ if the center acts on it by $z^{q_R}$. What phase does a center one-form symmetry operator linked once with $W_R(C)$ produce?

<details><summary><strong>Solution</strong></summary>

The linked center-symmetry operator acts by the center element on the Wilson line. Since $R$ has $N$-ality $q_R$, the action is

$$
W_R(C)\mapsto z^{q_R}W_R(C).
$$

If the linking number is $\ell$, the phase becomes

$$
z^{q_R\ell}.
$$

This is the one-form symmetry action by linking.

</details>

## References and further reading

- K. G. Wilson, original lattice-gauge-theory work introducing Wilson loops as gauge-invariant observables and confinement diagnostics.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the loop-dynamics and gauge-topology discussions.
- M. Srednicki, *Quantum Field Theory*, §82 for Wilson loops, lattice theory, and confinement.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25 for Yang–Mills theory and Wilson lines.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the one-form symmetry interpretation of Wilson lines.
- E. Witten, “Quantum Field Theory and the Jones Polynomial,” for Wilson loops in Chern–Simons theory.

## Version history

- 2026-06-19: First polished draft. Added gauge-transformation derivation, abelian and nonabelian definitions, representation/global-form discussion, static-potential diagnostic, center one-form symmetry action, renormalization caveats, and exercises.
