---
title: "What Is a Symmetry?"
description: "Defines an ordinary global symmetry in QFT as an action on observables and states, explains its Lagrangian and topological-operator presentations, and derives basic selection rules."
sidebar:
  label: "What Is a Symmetry?"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman, Weinberg, Srednicki, Zee; Gaiotto–Kapustin–Seiberg–Willett for the topological-operator formulation."
topics:
  - global symmetry
  - operator algebra
  - Hilbert space
  - selection rules
  - symmetry defects
canonicalTopics:
  - ordinary-global-symmetry
  - symmetry-action
  - topological-symmetry-operator
researchStatus:
  established:
    - "The operator and Hilbert-space definition of ordinary global symmetry is standard QFT material."
    - "The codimension-one topological-operator description is a now-standard way to connect ordinary symmetries to generalized symmetries."
  active:
    - "Non-invertible and higher-categorical extensions of the topological-operator viewpoint are active research areas and are only previewed here."
---

## Summary

A symmetry of a quantum field theory is not fundamentally a decorative transformation of letters in a Lagrangian. The durable statement is that a symmetry acts on the theory’s physical structures — states, operators, correlation functions, defects, boundary conditions, and sometimes background fields — while preserving the rules that make the theory the same theory.

For an ordinary internal global symmetry group $G$, the simplest Hilbert-space version is this: each group element $g\in G$ is represented by a unitary operator $U(g)$, and local operators transform by conjugation,

$$
g\cdot\mathcal O(x)=U(g)^\dagger\mathcal O(x)U(g).
$$

If the vacuum is invariant, correlation functions transform covariantly. For scalar local operators $\mathcal O_i$ transforming in representations $R_i$,

$$
\left\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\right\rangle
=
\left\langle (g\cdot\mathcal O_1)(x_1)\cdots (g\cdot\mathcal O_n)(x_n)\right\rangle.
$$

In a Lagrangian theory, a symmetry often appears as a transformation of fields that leaves the action invariant. That is useful, but it is not the final definition. A classical transformation becomes a quantum symmetry only if it also preserves the measure, regulator, operator algebra, and correlation functions. When this upgrade fails in a controlled way, the failure is called an anomaly.

A modern equivalent viewpoint represents an ordinary global symmetry element by a codimension-one topological operator $U_g(\Sigma_{d-1})$. Deforming this operator does not change correlators unless it crosses a charged insertion, and crossing the insertion applies the symmetry action. This viewpoint is the clean bridge from ordinary symmetries to higher-form, non-invertible, and symmetry-TFT language.

## Prerequisites

You should know the [Conventions and Notation](/symmetry-anomalies-topology/conventions/) for this volume, especially

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

You should also be comfortable with the basic QFT idea that local operators inserted in correlation functions are the main observables. Noether’s theorem, Ward identities, anomaly polynomials, and higher-form symmetries are not assumed here.

## Core idea

The word “symmetry” bundles together three related but different ideas.

First, there is the **abstract symmetry data**: a group $G$, or sometimes a more general algebraic structure, acting on the objects of the theory. For ordinary global symmetries, this action should preserve locality, operator products, time evolution, and the distinction between physical states.

Second, there is the **implementation** of that symmetry. In Hamiltonian language, this usually means unitary or antiunitary operators on the Hilbert space. In a path integral, it may mean a change of variables that leaves the quantum measure and action invariant. In Euclidean QFT, it may mean inserting a topological symmetry defect.

Third, there is a **presentation** of the symmetry in some chosen variables. A Lagrangian might show the symmetry as

$$
\Phi(x)\mapsto R(g)\Phi(x),
$$

where $\Phi$ is a multiplet of fields and $R(g)$ is a representation matrix. This is often the easiest way to compute. But it is not sacred. The same QFT may have a dual presentation using completely different fields.

The safest definition is therefore operator-first:

:::note[Working definition]
An ordinary internal global symmetry of a QFT is an action of a group $G$ on the physical operator algebra and Hilbert space, preserving correlation functions, locality, and time evolution, such that symmetry-related states and operators are physically distinct rather than gauge-equivalent descriptions of the same object.
:::

That last clause is the firewall separating global symmetry from gauge redundancy.

## Setup and conventions

This page focuses on ordinary internal global symmetries. “Ordinary” means zero-form: the symmetry acts on local operators and particle-like states. “Internal” means it does not move spacetime points. Spacetime and antiunitary symmetries require extra care and are treated later.

For a unitary internal symmetry group $G$, we write its action on the Hilbert space as

$$
g\mapsto U(g).
$$

Usually

$$
U(g_1g_2)=U(g_1)U(g_2),
$$

although quantum mechanics sometimes allows projective phases. Those phases are important and get their own preview page later in this chapter.

The action on a local operator is active and by conjugation:

$$
g\cdot\mathcal O(x)
=U(g)^\dagger\mathcal O(x)U(g).
$$

For a continuous symmetry near the identity, we write

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

with Hermitian charges $Q_a$. Expanding the conjugation action gives

$$
\delta_\alpha\mathcal O(x)
=\alpha^a\delta_a\mathcal O(x)+O(\alpha^2),
\qquad
\delta_a\mathcal O(x)=i[Q_a,\mathcal O(x)].
$$

For a field multiplet $\Phi$ in a representation $R$ with Hermitian generators $T_a^{(R)}$, a common convention is

$$
\delta_a\Phi=iT_a^{(R)}\Phi.
$$

Equivalently,

$$
[Q_a,\Phi]=T_a^{(R)}\Phi.
$$

:::note[Source note]
Different books place signs differently in $U(\alpha)$, $\delta\mathcal O$, and the Hermiticity convention for generators. The convention above is the one fixed in this volume’s Conventions and Notation page. It makes a unit-charge operator obey $U(\alpha)^\dagger\mathcal O_q U(\alpha)=e^{iq\alpha}\mathcal O_q$.
:::

## Symmetry as an action on a theory

A QFT is not just a set of classical equations. At minimum, it includes some collection of observables and a rule for computing correlation functions. Depending on the formalism, it may also include a Hilbert space, Hamiltonian, stress tensor, path-integral measure, local operator product expansion, line operators, boundary conditions, and allowed background fields.

A symmetry should preserve this structure. In a Hamiltonian theory on space $M_{d-1}$, a time-independent internal symmetry satisfies

$$
[U(g),H]=0.
$$

For continuous symmetry,

$$
[Q_a,H]=0.
$$

This implies that symmetry-related states have the same energy. If

$$
H|\psi\rangle=E|\psi\rangle,
$$

then

$$
H\,U(g)|\psi\rangle=E\,U(g)|\psi\rangle.
$$

In this basic sense, symmetry explains degeneracy. But degeneracy is only one symptom. The deeper statement is that all physical operations of the theory can be transported through the symmetry action.

For local operators, the symmetry should preserve operator products. Schematically, if

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}^{\ \ k}(x)\mathcal O_k(0),
$$

then the transformed operators must have a compatible product. Symmetry therefore constrains OPE coefficients, correlation functions, matrix elements, and effective actions.

For scattering theory, the same idea says that the S-matrix commutes with the symmetry:

$$
U(g)^\dagger S U(g)=S.
$$

This is why a statement about a field transformation in the Lagrangian becomes a selection rule for real processes.

## Lagrangian symmetries are presentations

Suppose a theory has fields $\Phi^I$ and action

$$
S[\Phi]=\int d^dx\,\mathcal L(\Phi,\partial\Phi).
$$

A classical symmetry is often introduced as a field transformation

$$
\Phi^I(x)\mapsto \Phi^{\prime I}(x),
$$

such that

$$
S[\Phi']=S[\Phi],
$$

or more generally the Lagrangian shifts by a total derivative. For continuous transformations this leads to Noether currents. For discrete transformations it usually leads directly to selection rules rather than currents.

This Lagrangian test is powerful, but it is only a test in a chosen presentation. To become a quantum symmetry, the change of variables must also preserve the path integral:

$$
Z=
\int \mathcal D\Phi\,e^{iS[\Phi]}.
$$

Formally, if both the action and measure are invariant,

$$
\mathcal D\Phi'=\mathcal D\Phi,
\qquad
S[\Phi']=S[\Phi],
$$

then the transformation gives a quantum symmetry. In real QFT, the word “formally” hides the regulator. A transformation can be a symmetry of the classical action and still fail after regularization. That is the beginning of anomaly theory.

:::caution[Classical invariance is not enough]
A classical field transformation that leaves $S$ invariant is a candidate symmetry. The quantum symmetry exists only after the measure, regulator, counterterms, and operator definitions are included. When no acceptable quantization preserves the candidate symmetry together with the other required structures, the symmetry is anomalous.
:::

The reverse can also happen: a symmetry of the quantum theory may be obscure in a particular Lagrangian. Dualities, bosonization, and emergent infrared symmetries are all reminders that fields are a language, not the object being described.

## First examples

### The real scalar with a sign flip

Consider a real scalar field with action

$$
S=\int d^dx\,\left[\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2-\frac{\lambda}{4!}\phi^4\right].
$$

It has a $\mathbb Z_2$ transformation

$$
\phi(x)\mapsto -\phi(x).
$$

The action is invariant because every term contains an even number of fields. If the vacuum and regulator preserve the symmetry, then correlation functions with an odd number of $\phi$ insertions vanish:

$$
\langle \phi(x_1)\phi(x_2)\cdots\phi(x_{2n+1})\rangle=0.
$$

This is a selection rule. It is not a mysterious perturbative accident. It follows because the operator product has odd $\mathbb Z_2$ charge.

If the theory is in a phase where

$$
\langle \phi\rangle\neq 0,
$$

then the action still has the $\mathbb Z_2$ symmetry, but the chosen vacuum does not. That is spontaneous symmetry breaking, not explicit breaking.

### The complex scalar with particle number symmetry

For a complex scalar field,

$$
\mathcal L=\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi
-\lambda(\phi^\dagger\phi)^2,
$$

there is a $U(1)$ transformation

$$
\phi(x)\mapsto e^{i\alpha}\phi(x),
\qquad
\phi^\dagger(x)\mapsto e^{-i\alpha}\phi^\dagger(x).
$$

With our convention,

$$
U(\alpha)^\dagger\phi(x)U(\alpha)=e^{i\alpha}\phi(x).
$$

Thus $\phi$ has charge $+1$ and $\phi^\dagger$ has charge $-1$. Correlators vanish unless the total charge is zero. For example,

$$
\langle \phi(x_1)\phi(x_2)\rangle=0,
\qquad
\langle \phi(x_1)\phi^\dagger(x_2)\rangle\neq 0
$$

is allowed by symmetry.

The conserved charge and Noether current are developed in the next chapter. For now, the important point is simpler: the symmetry assigns charges to operators, and charge conservation constrains what correlators can be nonzero.

## Selection rules from vacuum invariance

Selection rules are the first payoff of the operator definition.

Let $G=U(1)$ and let $\mathcal O_i$ be operators of charge $q_i$:

$$
U(\alpha)^\dagger\mathcal O_i(x)U(\alpha)
=e^{iq_i\alpha}\mathcal O_i(x).
$$

Assume the vacuum is invariant,

$$
U(\alpha)|0\rangle=|0\rangle.
$$

Then

$$
\begin{aligned}
\left\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\right\rangle
&=\left\langle 0\right|
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\left|0\right\rangle \\
&=\left\langle 0\right|
U(\alpha)^\dagger\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)U(\alpha)
\left|0\right\rangle \\
&=e^{i\alpha(q_1+\cdots+q_n)}
\left\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\right\rangle.
\end{aligned}
$$

Since this must hold for every $\alpha$, the correlator vanishes unless

$$
q_1+\cdots+q_n=0.
$$

For a nonabelian group, the same idea says that the tensor product of representations carried by the inserted operators must contain the trivial representation for a singlet correlator to be allowed.

:::note[Selection rule]
For an invariant vacuum, a correlator of charged operators can be nonzero only if the product of their symmetry representations contains a singlet. For $U(1)$, this reduces to total charge zero.
:::

This argument is intentionally independent of perturbation theory. It applies whether the theory is weakly coupled, strongly coupled, Lagrangian, non-Lagrangian, or solved only through symmetry data.

## Symmetry operators as topological defects

There is a second way to say the same thing that becomes indispensable later.

In Euclidean spacetime, an ordinary global symmetry element $g\in G$ can be represented by a codimension-one operator

$$
U_g(\Sigma_{d-1}),
$$

where $\Sigma_{d-1}$ is a closed oriented hypersurface. The defining property is topological invariance: as long as $\Sigma_{d-1}$ is deformed without crossing operator insertions, the correlation function is unchanged.

When $\Sigma_{d-1}$ crosses a local operator, it applies the symmetry action. If local operators $\mathcal O_i$ form a multiplet, then crossing gives

$$
U_g(\Sigma_{d-1})\,\mathcal O_i(x)
\quad\leadsto\quad
R_i^{\ j}(g)\mathcal O_j(x).
$$

:::note[Source note]
The notation $U_g(\Sigma_{d-1})$ follows the generalized-symmetry literature, specialized here to ordinary zero-form symmetry. Orientation conventions can invert $g$ when the surface is crossed in the opposite direction; this page uses the convention that sweeping $U_g$ past an operator from left to right applies $R(g)$.
:::

<figure class="doc-figure" style="--figure-width: 42rem;">

![A codimension-one topological symmetry operator being swept across a local operator, applying the symmetry action.](/figures/symmetry-anomalies-topology/ordinary-symmetry-topological-operator.svg)

<figcaption>

An ordinary global symmetry element $g$ can be represented by a codimension-one topological operator $U_g(\Sigma_{d-1})$. Deforming $\Sigma_{d-1}$ changes nothing until it crosses a local operator; crossing applies the representation $R(g)$ to that operator.

</figcaption>
</figure>

This picture packages selection rules geometrically. Put all local insertions inside a large closed symmetry surface. Because the surface is topological, shrink it to nothing. If the product of symmetry actions on the insertions is nontrivial, the correlator must vanish.

For an ordinary $U(1)$ symmetry, crossing an operator of charge $q$ gives a phase

$$
\mathcal O_q\mapsto e^{iq\alpha}\mathcal O_q.
$$

Shrinking a large symmetry surface around several insertions gives

$$
e^{i\alpha(q_1+\cdots+q_n)}=1
$$

for every $\alpha$, again implying total charge zero.

:::note[Why introduce this so early?]
The topological-operator language may feel like overkill for ordinary symmetries, where Hilbert-space charges are familiar. It pays off later because higher-form symmetries, non-invertible symmetries, defects, gauging, and anomaly inflow are naturally phrased in the same language.
:::

## What data specifies an ordinary symmetry?

For many calculations, saying “the theory has symmetry $G$” is not enough. A useful symmetry specification includes at least the following data.

| Data | Meaning | Why it matters |
|---|---|---|
| Symmetry group $G$ | The abstract group law | Determines composition of transformations. |
| Action on local operators | $\mathcal O_i\mapsto R_i^{\ j}(g)\mathcal O_j$ | Determines selection rules and operator multiplets. |
| Action on states | $|\psi\rangle\mapsto U(g)|\psi\rangle$ | Determines degeneracies and charge sectors. |
| Vacuum behavior | Whether $U(g)|0\rangle=|0\rangle$ | Distinguishes unbroken and spontaneously broken symmetry. |
| Faithful quotient | Whether any subgroup acts trivially on all observables | Determines the actual physical symmetry. |
| Global form | The group, not just its Lie algebra | Controls allowed charges, bundles, and background fields. |
| Background coupling | Which classical fields can probe the symmetry | Prepares gauging and anomaly tests. |
| Possible projective phases | Whether $U(g_1)U(g_2)$ equals $U(g_1g_2)$ only up to a phase | Signals central extensions, spin structures, or anomaly-like data. |

The “faithful quotient” is worth pausing on. If a subgroup $K\subset G$ acts trivially on every genuine operator and state, then the effective symmetry acting on the theory is not $G$ but

$$
G_{\mathrm{eff}}=G/K.
$$

Physicists often say “the theory has $G$ symmetry” when a larger group is convenient in a Lagrangian, even if only a quotient acts faithfully on gauge-invariant objects. That shortcut becomes dangerous when discussing line operators, background fields, and anomalies.

## Symmetry of a state versus symmetry of a theory

A theory may have a symmetry even if a state does not. This distinction is essential.

Let $U(g)$ commute with the Hamiltonian. Then $g$ is a symmetry of the theory. A particular state $|\Omega\rangle$ is invariant only if

$$
U(g)|\Omega\rangle=e^{i\theta_g}|\Omega\rangle.
$$

The phase is physically irrelevant for a single state vector, so it is allowed. If this fails, the state breaks the symmetry. The classic case is a ferromagnet: the Hamiltonian may be rotation invariant, but a ground state with magnetization pointing in one chosen direction is not.

In QFT, spontaneous symmetry breaking is especially subtle because infinite volume can support distinct superselection sectors. The symmetry may map one vacuum to another, while no finite-energy local operation connects them. This is why the phrase “the symmetry is broken” usually means “the chosen vacuum is not invariant,” not “the equations forgot the symmetry.”

The unbroken subgroup of a vacuum $|\Omega\rangle$ is

$$
H=\{g\in G\mid U(g)|\Omega\rangle=e^{i\theta_g}|\Omega\rangle\}.
$$

The broken generators live in $G/H$ and lead, under appropriate assumptions, to Goldstone modes. That story belongs to the Spontaneous Symmetry Breaking chapter.

## Internal, spacetime, and antiunitary symmetries

This page mostly discusses internal unitary symmetries. They act on fields and operators without moving their spacetime arguments:

$$
\mathcal O_i(x)\mapsto R_i^{\ j}(g)\mathcal O_j(x).
$$

Spacetime symmetries are different because they also move points:

$$
\mathcal O_i(x)\mapsto R_i^{\ j}(\Lambda)\mathcal O_j(\Lambda^{-1}x).
$$

Translations, rotations, Lorentz transformations, scale transformations, and conformal transformations belong here. Their currents include the stress tensor and angular-momentum currents rather than just internal Noether currents.

Antiunitary symmetries, especially time reversal, are different again. They conjugate complex numbers:

$$
T(c_1|\psi_1\rangle+c_2|\psi_2\rangle)
=c_1^*T|\psi_1\rangle+c_2^*T|\psi_2\rangle.
$$

This changes the way phases, commutators, and path-integral weights transform. Antiunitary symmetries are treated later with parity, time reversal, charge conjugation, CPT, reflection positivity, and spin structures.

## Global symmetry is not gauge redundancy

A global symmetry maps a physical state or operator to another physical state or operator. A gauge transformation maps a description to an equivalent description. This is not semantic fussing; it changes what counts as an observable.

For an ordinary global $U(1)$ symmetry, a charged operator can be physical:

$$
\mathcal O_q\mapsto e^{iq\alpha}\mathcal O_q.
$$

For a gauge redundancy, gauge-variant local fields are not physical observables by themselves. Physical operators must be gauge-invariant, or must be dressed in a way compatible with gauge constraints and boundary conditions.

This is why “local symmetry” is a dangerous phrase. In most QFT contexts, a local gauge transformation is not a physical symmetry operation. It is redundancy introduced to describe constrained degrees of freedom efficiently.

There are important refinements: large gauge transformations, boundary charges, asymptotic symmetries, one-form symmetries, and global forms of gauge groups can all produce physical symmetry data. But those refinements make sense only after the basic distinction is clean.

:::caution[The most common trap]
Do not define a physical symmetry as “a transformation with an arbitrary function parameter.” That definition describes gauge redundancy in many examples. A physical global symmetry is diagnosed by its action on gauge-invariant observables, states, defects, and boundary data.
:::

## Symmetry can be emergent, accidental, or hidden

A microscopic Lagrangian may have less symmetry than its infrared limit. This can happen because symmetry-breaking operators are irrelevant under RG flow, or because the effective degrees of freedom reorganize in a way that makes a larger symmetry manifest.

Such an infrared symmetry is called **emergent**. It is real in the low-energy theory even if it is not exact in the ultraviolet completion. In condensed-matter systems, emergent symmetries are common near critical points. In high-energy QFT, accidental symmetries often appear in effective field theories because the lowest-dimension operators happen to respect more symmetry than the microscopic theory.

A symmetry may also be **hidden** in a chosen description. For example, a duality may map a symmetry acting simply on one set of variables to a nonlocal or topological action in another. This is one reason the operator-first viewpoint is safer than a field-first viewpoint.

Finally, a candidate symmetry can be **explicitly broken** by terms in the action. If the complex scalar theory includes

$$
\Delta\mathcal L=\epsilon\phi^2+\epsilon^*(\phi^\dagger)^2,
$$

then the full $U(1)$ symmetry is absent, although a $\mathbb Z_2$ subgroup may remain. Explicit breaking is not an anomaly and not spontaneous breaking. It just means the symmetry was not a symmetry of the theory being studied.

## Common pitfalls

**Defining symmetry only from the Lagrangian.** Lagrangian invariance is useful but presentation-dependent. The quantum theory cares about the measure, regulator, operator algebra, and allowed observables.

**Confusing covariance with invariance.** A charged operator is not invariant under a symmetry. It transforms covariantly. The theory can be symmetric precisely because it contains nontrivially transforming operators.

**Forgetting the vacuum.** Selection rules assume an invariant state. If the vacuum breaks the symmetry, correlators need not obey the naive unbroken selection rules.

**Treating gauge transformations as physical global symmetries.** Gauge-variant fields can be useful variables, but physical statements must be made in gauge-invariant language or with carefully specified boundary/dressing data.

**Ignoring the global form of the group.** The Lie algebra sees infinitesimal transformations. It does not know which charges are allowed, which bundles exist, or which topological operators are genuine.

**Assuming all symmetries have Noether currents.** Continuous ordinary symmetries often do. Discrete symmetries do not have ordinary Noether currents. Higher-form symmetries have generalized currents. Non-invertible symmetries are better described by defects.

**Assuming symmetry must be invertible.** Ordinary group symmetries are invertible by definition. Later chapters discuss non-invertible symmetry defects, where fusion does not give a group.

## Relations to other pages

This page is the entry point for the Ordinary Global Symmetries chapter. The next conceptual steps are Internal Versus Spacetime Symmetries, Continuous and Discrete Symmetries, Symmetry Groups and Representations, and Action on Fields and Operators.

The Noether Currents and Ward Identities chapter turns continuous symmetries into local current conservation equations and correlation-function identities. Background Fields and Gauging explains how to probe a symmetry with classical sources and why anomalies are obstructions to gauging. Gauge Redundancy and BRST explains why gauge transformations are not ordinary global symmetries. Higher-Form and Generalized Symmetries generalizes the topological-operator viewpoint introduced here.

## Research status

The core material on ordinary global symmetries is settled. The operator and Hilbert-space viewpoint goes back to the foundations of quantum mechanics and QFT, while the Lagrangian, Noether, and Ward-identity viewpoints are standard across graduate texts.

The topological-operator phrasing is modern but no longer exotic. It is the standard way to unify ordinary global symmetries with higher-form symmetries and defects. What remains active is the broader research program: non-invertible symmetry, categorical symmetry, symmetry TFT, subsystem symmetry, higher groups, and their roles in RG flows and quantum gravity.

For this page, the topological-defect language is used only in its stable ordinary-symmetry form: codimension-one invertible symmetry operators implementing elements of a group.

## Exercises

### Exercise 1: Odd correlators in a $\mathbb Z_2$-symmetric scalar theory

Consider a real scalar theory whose quantum measure and action are invariant under $\phi\mapsto -\phi$. Show that

$$
\langle \phi(x_1)\cdots\phi(x_{2n+1})\rangle=0
$$

in a $\mathbb Z_2$-invariant vacuum.

<details><summary><strong>Solution</strong></summary>

Use the path-integral expression

$$
\langle \phi(x_1)\cdots\phi(x_{2n+1})\rangle
=\frac{1}{Z}\int\mathcal D\phi\,\phi(x_1)\cdots\phi(x_{2n+1})e^{iS[\phi]}.
$$

Change variables to $\phi'=-\phi$. Invariance of the measure and action gives

$$
\mathcal D\phi'=\mathcal D\phi,
\qquad
S[\phi']=S[\phi].
$$

The operator insertion changes sign because it contains an odd number of fields:

$$
\phi'(x_1)\cdots\phi'(x_{2n+1})
=-\phi(x_1)\cdots\phi(x_{2n+1}).
$$

Therefore the correlator equals minus itself, so it vanishes.

</details>

### Exercise 2: The $U(1)$ selection rule

Let $\mathcal O_i$ have $U(1)$ charge $q_i$ in the convention

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)=e^{iq_i\alpha}\mathcal O_i.
$$

Assume $U(\alpha)|0\rangle=|0\rangle$. Show that the correlator $\langle \mathcal O_1\cdots\mathcal O_n\rangle$ vanishes unless $\sum_i q_i=0$.

<details><summary><strong>Solution</strong></summary>

Insert the identity $U(\alpha)U(\alpha)^\dagger=1$ and use vacuum invariance:

$$
\begin{aligned}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
&=\langle0|U(\alpha)^\dagger\mathcal O_1\cdots\mathcal O_nU(\alpha)|0\rangle\\
&=e^{i\alpha\sum_i q_i}\langle \mathcal O_1\cdots\mathcal O_n\rangle.
\end{aligned}
$$

If $\sum_iq_i\neq0$, choose $\alpha$ so that $e^{i\alpha\sum_iq_i}\neq1$. The only number equal to a nontrivial phase times itself is zero. Therefore the correlator vanishes unless total charge is zero.

</details>

### Exercise 3: Charge convention check

With

$$
U(\alpha)=e^{-i\alpha Q},
\qquad
\delta\mathcal O=i[Q,\mathcal O],
$$

suppose $[Q,\mathcal O_q]=q\mathcal O_q$. Show that

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{iq\alpha}\mathcal O_q.
$$

<details><summary><strong>Solution</strong></summary>

For small $\alpha$,

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)
=e^{i\alpha Q}\mathcal O_qe^{-i\alpha Q}
=\mathcal O_q+i\alpha[Q,\mathcal O_q]+O(\alpha^2).
$$

Using $[Q,\mathcal O_q]=q\mathcal O_q$ gives

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)
=(1+iq\alpha+O(\alpha^2))\mathcal O_q.
$$

Exponentiating the infinitesimal result gives

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{iq\alpha}\mathcal O_q.
$$

</details>

### Exercise 4: Topological operator derivation of charge neutrality

In Euclidean spacetime, represent a $U(1)$ symmetry transformation by a closed codimension-one topological operator $U_\alpha(\Sigma)$. Suppose crossing an operator $\mathcal O_{q_i}(x_i)$ gives a phase $e^{iq_i\alpha}$. Explain why a correlator of insertions inside a large closed $\Sigma$ vanishes unless $\sum_iq_i=0$.

<details><summary><strong>Solution</strong></summary>

Because $U_\alpha(\Sigma)$ is topological, its insertion can be deformed without changing the correlator as long as it does not cross operator insertions.

Start with $\Sigma$ surrounding all insertions. Shrink $\Sigma$ to nothing. If it crosses each insertion during the shrink, the correlator is multiplied by

$$
\prod_i e^{iq_i\alpha}=e^{i\alpha\sum_iq_i}.
$$

But after the surface has shrunk to nothing, there is no remaining operator insertion. Therefore the original correlator must equal

$$
e^{i\alpha\sum_iq_i}
$$

times itself for every $\alpha$. Unless $\sum_iq_i=0$, this forces the correlator to vanish.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Operator-oriented discussion of spacetime and internal symmetries.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 2. Foundational discussion of symmetries in quantum theory, including unitary and antiunitary implementations.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24. Continuous, discrete, and nonabelian symmetries in Lagrangian QFT.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapter I.10 and related symmetry-breaking chapters. Efficient physical motivation for symmetry as an organizing principle.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 3, 8, 14, and 28–30. Noether theorem, gauge symmetry, Ward identities, symmetry breaking, and anomalies in a calculation-oriented style.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Introduces the topological-operator viewpoint that later pages generalize.

## Version history

- **2026-06-16:** Initial polished page defining ordinary global symmetry and introducing the topological-operator viewpoint.
