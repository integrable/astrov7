---
title: "Coupling Renormalization"
description: "How interaction strengths are defined by vertex counterterms, subtraction schemes, scale dependence, and renormalization conditions in perturbative QFT."
sidebar:
  label: "Coupling Renormalization"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§16–20 and 27–28; Coleman 2019, chs. 15–16, 23, 25, and 50; Weinberg 1995, Vol. I, ch. 12 and Vol. II, ch. 18; Schwartz 2014, chs. 19–23; Zinn-Justin 2021, chs. 8–10"
topics:
  - coupling renormalization
  - vertex counterterms
  - beta functions
  - running couplings
  - renormalization schemes
canonicalTopics:
  - coupling-renormalization
  - vertex-counterterm
  - running-coupling
  - beta-function
  - momentum-subtraction
researchStatus:
  established:
    - "Coupling renormalization is the standard procedure that fixes local interaction counterterms and defines scale-dependent renormalized couplings through vertex functions or subtraction schemes."
  active:
    - "Precision gauge theory, EFT matching, threshold decoupling, multi-coupling flows, evanescent operators, and nonperturbative coupling definitions require scheme-aware refinements beyond the scalar examples on this page."
---

## Summary

**Coupling renormalization** fixes the parameters multiplying interaction operators. Self-energies renormalize propagation; vertex corrections renormalize interactions.

For scalar $\phi^4$ theory in dimensional regularization,

$$
\mathcal L_{\rm int}+\mathcal L_{\rm ct}
=
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4,
$$

so the tree-level and counterterm four-point vertices are

$$
{\mathcal V_4^{(0)}=-i\mu^{2\epsilon}\lambda,}
\qquad
{\mathcal V_{4,{\rm ct}}=-i\mu^{2\epsilon}\delta\lambda.}
$$

At one loop, the local ultraviolet part of the four-point vertex is canceled by $\delta\lambda$. In the qft.org $d=4-2\epsilon$ convention used in the preceding vertex-correction pages,

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
+O(\lambda^3),
$$

and the corresponding four-dimensional one-loop beta function is

$$
\beta_\lambda
\equiv
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Coupling renormalization turns loop-corrected vertex functions plus local counterterms into finite scheme-defined couplings and running parameters](/figures/perturbative-qft/coupling-renormalization-map.svg)

<figcaption>

Coupling renormalization is the vertex analogue of mass renormalization. Loop vertex corrections contain a local ultraviolet part and a finite nonlocal part. The local part is absorbed into a counterterm; the remaining finite vertex defines a coupling through either a physical subtraction condition or an algebraic scheme such as $\overline{\mathrm{MS}}$.

</figcaption>
</figure>

The coupling is not the value of a single diagram. It is a scheme-defined coordinate on an interaction, extracted from a specified vertex, amplitude, or observable.

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Mass Renormalization](/perturbative-qft/renormalized-perturbation-theory/mass-renormalization/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/).

For the scattering meaning of vertex functions, review [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) and [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/).

## Core idea

A coupling is defined by a rule for reading an interaction strength from a quantum-corrected object.

At tree level, the scalar term

$$
-
\frac{\lambda}{4!}\phi^4
$$

just gives the four-point vertex $-i\lambda$. At loop level, the four-point interaction becomes momentum-dependent:

$$
-i\lambda
\quad\longrightarrow\quad
\Gamma_4(p_1,p_2,p_3,p_4).
$$

The loop-corrected vertex contains two different kinds of information:

$$
\text{local UV part}
\quad+
\text{finite nonlocal momentum dependence}.
$$

The local UV part has the same form as a local interaction operator and is absorbed into a counterterm. The finite nonlocal part remains in amplitudes. A renormalization condition then says which finite part is called the renormalized coupling.

This is why phrases like “the coupling is the coefficient in the Lagrangian” are incomplete after loops. The coefficient in the renormalized Lagrangian is the coupling in a particular scheme. Changing the scheme changes the coordinate, not the physical prediction.

## Setup and conventions

We use qft.org mostly-minus conventions. In scalar $\phi^4$ examples,

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\rm ct}
\supset
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

Thus

$$
\mathcal V_{4,{\rm ct}}=-i\mu^{2\epsilon}\delta\lambda.
$$

We use

$$
d=4-2\epsilon,
\qquad
\frac{1}{\overline\epsilon}
=
\frac{1}{\epsilon}-\gamma_E+\ln4\pi.
$$

The bare quartic interaction can be written as

$$
-
\frac{\lambda_0}{4!}\phi_0^4
=
-
\frac{Z_\phi^2\lambda_0}{4!}\phi^4.
$$

The counterterm split used in this chapter is

$$
Z_\phi^2\lambda_0
=
\mu^{2\epsilon}\left(\lambda+\delta\lambda\right).
$$

This formula is a definition of the split between the renormalized coupling and its counterterm. Other notations, such as $\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda$, are equivalent after translating how the field-strength factors are distributed.

## Couplings from vertex functions

The natural object for coupling renormalization is a 1PI vertex function. For $\phi^4$ theory, suppress the overall momentum-conserving delta function and write the diagrammatic four-point vertex factor as

$$
\mathcal V_4(s,t,u)
=
-i\lambda
+\mathcal V_4^{(1)}(s,t,u)
-i\delta\lambda
+O(\lambda^3).
$$

Here $s,t,u$ are the Mandelstam invariants. The one-loop correction $\mathcal V_4^{(1)}$ is not a constant. It contains logarithms and threshold structure. A local counterterm can cancel only the constant ultraviolet pole part.

A momentum-subtraction condition might define the coupling by

$$
\mathcal V_4(s_*,t_*,u_*)=-i\lambda_R
$$

at some fixed Euclidean subtraction point. In that case, $\delta\lambda$ is chosen so that the full loop-corrected vertex equals the prescribed value at that point.

Minimal subtraction instead defines $\lambda(\mu)$ by pole removal:

$$
\text{MS coupling} = \text{parameter left after subtracting UV poles.}
$$

No physical kinematic point is selected. This makes MS simple and algebraic, but it means the coupling must later be matched to a measured quantity or to another scheme.

## One-loop φ⁴ example

For

$$
\mathcal L_{\rm int}
=-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

the one-loop four-point vertex correction is the sum of the $s$, $t$, and $u$ channel fish diagrams:

$$
\mathcal V_4^{(1)}(s,t,u)
=
\frac{(-i\lambda)^2}{2}\left[I(s)+I(t)+I(u)\right].
$$

The factor $1/2$ is the symmetry factor of each fish diagram. The channel integral is

$$
I(P^2)
=
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon}.
$$

With the bubble convention used earlier in this volume, the ultraviolet pole in the sum of channels is

$$
\mathcal V_{4,{\rm div}}^{(1)}
=
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

The counterterm vertex is

$$
\mathcal V_{4,{\rm ct}}=-i\delta\lambda.
$$

Cancellation of the pole requires

$$
-i\delta\lambda
+
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}=0,
$$

so

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
+O(\lambda^3).
$$

Only the local pole is subtracted. The finite logarithms

$$
\ln\frac{m^2-x(1-x)P^2-i\epsilon}{\mu^2}
$$

remain in the renormalized vertex and are responsible for the scale dependence of the perturbative coupling.

:::note[Do not overread this example]
The scalar $\phi^4$ coupling is a clean one-coupling example. In gauge theories, Yukawa theories, and EFTs, several couplings and fields can mix. Coupling renormalization then becomes matrix-valued bookkeeping constrained by symmetries.
:::

## Running from bare scale independence

The bare coupling is independent of the arbitrary renormalization scale:

$$
\mu\frac{d\lambda_0}{d\mu}=0.
$$

For the one-loop scalar example, write the pole coefficient as

$$
a=\frac{3}{32\pi^2},
$$

so the bare coupling has the form

$$
\lambda_0
=
\mu^{2\epsilon}
\left[
\lambda+
\frac{a\lambda^2}{\epsilon}
+O(\lambda^3)
\right],
$$

using the same pole convention as [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/). Define the $d$-dimensional beta function at fixed bare coupling:

$$
\beta_\lambda^{(d)}
=
\mu\frac{d\lambda}{d\mu}\bigg|_{\lambda_0}.
$$

Solving order by order gives

$$
\beta_\lambda^{(d)}
=
-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

Therefore in four dimensions,

$$
\beta_\lambda
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

The important lesson is not just the coefficient. The important lesson is structural:

$$
\text{UV pole coefficient}
\quad\Longrightarrow\quad
\text{renormalization-group running}.
$$

The running coupling keeps physical quantities independent of the arbitrary scale $\mu$ when all terms at a given perturbative order are included.

## Momentum-subtraction couplings

In a momentum-subtraction scheme, the coupling is defined by a vertex value at a specified kinematic point. For example, choose a Euclidean symmetric point with

$$
s_*=t_*=u_*=-Q^2,
$$

with the precise relation among $s,t,u$ chosen consistently with the external masses. Define

$$
\mathcal V_4(s_*,t_*,u_*)=-i\lambda_{\rm MOM}(Q).
$$

At one loop,

$$
-i\lambda-i\delta\lambda_{\rm MOM}
+\mathcal V_4^{(1)}(s_*,t_*,u_*)
=
-i\lambda_{\rm MOM}(Q).
$$

If the renormalized parameter in the Lagrangian is already called $\lambda_{\rm MOM}(Q)$, then the counterterm is chosen to cancel the loop correction at the subtraction point:

$$
-i\delta\lambda_{\rm MOM}
+
\mathcal V_4^{(1)}(s_*,t_*,u_*)=0.
$$

Unlike minimal subtraction, this condition removes a finite part as well as the pole. That finite subtraction is not wrong. It is the definition of the scheme.

Momentum-subtraction schemes are physically intuitive because they define couplings through vertex values. MS schemes are algebraically efficient because they define couplings through pole parts. Both are useful.

## Scheme dependence

A finite redefinition of a coupling is a change of coordinates:

$$
\lambda'
=
\lambda+c_1\lambda^2+c_2\lambda^3+\cdots.
$$

The beta function transforms by the chain rule:

$$
\beta_{\lambda'}(\lambda')
=
\frac{d\lambda'}{d\lambda}\,\beta_\lambda(\lambda).
$$

For a single marginal coupling with

$$
\beta_\lambda=b_1\lambda^2+b_2\lambda^3+\cdots,
$$

the first nonzero coefficient $b_1$ is invariant under a regular finite redefinition of the form above. Higher coefficients can change.

In theories with several couplings,

$$
g^a\mapsto g'^a(g),
$$

the beta functions form a vector field on coupling space:

$$
\beta'^a(g')=
\frac{\partial g'^a}{\partial g^b}\,\beta^b(g).
$$

This geometric viewpoint is useful because it stops one from asking whether the coordinate $g^a$ is itself physical. Observables and RG-invariant statements are physical; a particular coordinate on coupling space is a convention.

## Gauge and Yukawa couplings: preview

In a Yukawa theory,

$$
\mathcal L_{\rm int}=-y\phi\overline\psi\psi,
$$

the coupling counterterm receives contributions from the three-point vertex correction and from field-strength renormalization of $\phi$ and $\psi$. The bare coupling can be written schematically as

$$
y_0=\mu^\epsilon Z_y y,
$$

with $Z_y$ determined by the chosen three-point function and field normalizations.

In QED, one often writes

$$
e_0=\mu^\epsilon Z_e e.
$$

The electron-photon vertex counterterm, electron field-strength renormalization, and photon field-strength renormalization are not independent. The Ward identity implies a relation usually summarized as

$$
Z_1=Z_2,
$$

so charge renormalization is controlled by the photon field-strength factor:

$$
Z_e=Z_A^{-1/2}
$$

in the corresponding convention. In non-Abelian gauge theory, Slavnov–Taylor identities play the analogous role, and the beta function is constrained by gauge symmetry, ghosts, gauge boson self-interactions, and matter representations.

The detailed gauge-theory story belongs to the gauge-theory perturbation chapter. The point here is simple: coupling renormalization is not always just “renormalize the vertex diagram.” Symmetries can tie vertex and field counterterms together.

## Couplings versus observables

A renormalized coupling is useful because it lets many observables be expressed efficiently. It is not itself an observable until a measurement prescription is specified.

For example, an amplitude may have the schematic form

$$
\mathcal M(Q)
=
\lambda(\mu)
+
\lambda^2(\mu)
\left[c\ln\frac{Q^2}{\mu^2}+f\right]
+O(\lambda^3).
$$

The explicit logarithm depends on $\mu$, and the running of $\lambda(\mu)$ also depends on $\mu$. The physical amplitude is independent of $\mu$ up to neglected higher orders:

$$
\mu\frac{d}{d\mu}\mathcal M(Q)=O(\lambda^3)
$$

for a one-loop calculation.

The best choice of $\mu$ is often near the characteristic momentum scale $Q$, because that minimizes large logarithms. This is a calculational strategy, not a new physical law.

## Relevant, marginal, and irrelevant couplings

Near four dimensions, the quartic scalar coupling is marginal at the engineering level:

$$
[\lambda]=0
\qquad(d=4).
$$

Dimensional regularization keeps track of this by writing

$$
[\lambda]=0,
\qquad
[\lambda_0]=2\epsilon
\qquad(d=4-2\epsilon),
$$

with the factor $\mu^{2\epsilon}$ inserted into the interaction.

Other couplings behave differently. A mass-squared parameter has positive mass dimension and is relevant. A higher-derivative operator such as

$$
\frac{c_6}{\Lambda^2}\phi^6
$$

in four dimensions is irrelevant at weak coupling. Its coefficient still renormalizes, but its power counting and physical interpretation are EFT data rather than ordinary renormalizable-coupling data.

Coupling renormalization therefore depends on the operator being renormalized:

| Operator type | Coupling behavior | Typical role |
|---|---|---|
| Relevant | Positive mass dimension | Masses, symmetry-breaking deformations |
| Marginal | Dimensionless classically | Gauge, Yukawa, quartic scalar couplings |
| Irrelevant | Negative mass dimension | EFT corrections suppressed by a heavy scale |

The perturbative machinery is similar in all cases. The interpretation under RG flow differs.

## Common pitfalls

**Defining a coupling without saying the scheme.** A coupling must be defined by a renormalization condition, a subtraction scheme, or a physical observable.

**Removing finite nonlocal terms with a local counterterm.** A local counterterm can cancel local polynomial UV pieces. It cannot remove thresholds, branch cuts, or nonlocal logarithmic dependence on external momenta.

**Forgetting field-strength factors.** Coupling counterterms are tied to field normalizations. In gauge theories, Ward or Slavnov–Taylor identities can make this relation essential.

**Confusing running with time dependence.** A running coupling depends on the arbitrary renormalization scale $\mu$, not on time. The $\mu$ dependence organizes how calculations at different scales are described.

**Assuming MS automatically decouples heavy particles.** In mass-independent schemes, heavy fields can continue to appear in beta functions below threshold unless one matches to an effective theory.

**Treating a Landau pole as a one-diagram fact.** A beta function is a perturbative object with a domain of validity. Conclusions about UV completion require more than extrapolating a one-loop formula beyond its regime.

## Relations to other pages

- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) derives the one-loop scalar diagrams that motivate coupling counterterms.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) explains pole subtraction and beta-function extraction.
- [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) explains momentum-subtraction and physical renormalization prescriptions.
- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) shows how coupling counterterms arise from the bare Lagrangian.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) translates the local coupling counterterm into diagrammatic rules.
- [Mass Renormalization](/perturbative-qft/renormalized-perturbation-theory/mass-renormalization/) treats the relevant-coupling analogue for two-point functions.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) explains the tree-level amplitude that coupling renormalization corrects.

## Research status

- **Established:** Coupling renormalization, vertex counterterms, scheme dependence, and beta functions are standard perturbative QFT technology.
- **Active:** Multi-loop beta functions, threshold matching, EFT anomalous-dimension matrices, evanescent operators, infrared subtraction, gauge-invariant definitions of effective couplings, and precision Standard Model running remain active technical areas.
- **Speculative:** Extrapolating perturbative running into regimes of strong coupling or far beyond measured scales can suggest possibilities, but it is not by itself a nonperturbative conclusion.

## Exercises

### Exercise 1: Counterterm from the φ⁴ fish diagrams

Suppose the divergent part of the one-loop four-point vertex in $\phi^4$ theory is

$$
\mathcal V_{4,{\rm div}}^{(1)}
=
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

Using the counterterm vertex $-i\delta\lambda$, find $\delta\lambda_{\overline{\mathrm{MS}}}$.

<details>
<summary><strong>Solution</strong></summary>

The divergent part of the renormalized vertex is

$$
\mathcal V_{4,{\rm div}}^{(1)}+\mathcal V_{4,{\rm ct}}
=
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
-i\delta\lambda.
$$

Canceling the pole requires

$$
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
-i\delta\lambda=0.
$$

Therefore

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

</details>

### Exercise 2: Beta function from a pole coefficient

Let

$$
\lambda_0
=
\mu^{2\epsilon}
\left[
\lambda+
\frac{a\lambda^2}{\epsilon}
+O(\lambda^3)
\right].
$$

Show that

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate at fixed $\lambda_0$:

$$
0=
\mu\frac{d}{d\mu}
\left\{
\mu^{2\epsilon}
\left[\lambda+\frac{a\lambda^2}{\epsilon}\right]
\right\}.
$$

Dividing by $\mu^{2\epsilon}$ gives

$$
0=
2\epsilon\left[\lambda+\frac{a\lambda^2}{\epsilon}\right]
+
\beta_\lambda^{(d)}
\left[1+\frac{2a\lambda}{\epsilon}\right]
+O(\lambda^3).
$$

Use

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+b\lambda^2+O(\lambda^3).
$$

Then the term $(2a\lambda/\epsilon)\beta_\lambda^{(d)}$ contributes $-4a\lambda^2$ at this order. The coefficient of $\lambda^2$ is

$$
2a+b-4a=b-2a.
$$

Setting it to zero gives $b=2a$, so

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

</details>

### Exercise 3: Momentum-subtraction counterterm

Suppose

$$
\mathcal V_4(s,t,u)
=
-i\lambda-i\delta\lambda+\mathcal V_4^{(1)}(s,t,u)
$$

and impose

$$
\mathcal V_4(s_*,t_*,u_*)=-i\lambda_R.
$$

Solve for $\delta\lambda$.

<details>
<summary><strong>Solution</strong></summary>

At the subtraction point,

$$
-i\lambda-i\delta\lambda+\mathcal V_4^{(1)}(s_*,t_*,u_*)=-i\lambda_R.
$$

Move the tree term and loop term to the other side:

$$
-i\delta\lambda
=
-i\lambda_R+i\lambda-
\mathcal V_4^{(1)}(s_*,t_*,u_*).
$$

Multiplying by $i$ gives

$$
\delta\lambda
=
\lambda_R-
\lambda
-
i\,\mathcal V_4^{(1)}(s_*,t_*,u_*).
$$

If the parameter in the Lagrangian is already chosen to be $\lambda_R$ at tree level, set $\lambda=\lambda_R$ in this formula.

</details>

### Exercise 4: Scheme change and the first beta coefficient

Let

$$
\lambda'=\lambda+c\lambda^2+O(\lambda^3),
\qquad
\beta_\lambda=b_1\lambda^2+O(\lambda^3).
$$

Show that the first beta-function coefficient is unchanged in the primed coupling.

<details>
<summary><strong>Solution</strong></summary>

The beta function transforms as

$$
\beta_{\lambda'}=
\frac{d\lambda'}{d\lambda}\beta_\lambda.
$$

Since

$$
\frac{d\lambda'}{d\lambda}=1+2c\lambda+O(\lambda^2),
$$

we get

$$
\beta_{\lambda'}
=
(1+2c\lambda+\cdots)
\left[b_1\lambda^2+O(\lambda^3)\right]
=
b_1\lambda^2+O(\lambda^3).
$$

To this order, $\lambda=\lambda'+O(\lambda'^2)$, so

$$
\beta_{\lambda'}=b_1\lambda'^2+O(\lambda'^3).
$$

Thus the first nonzero beta-function coefficient of a single marginal coupling is unchanged by this finite redefinition.

</details>

### Exercise 5: Locality of the coupling counterterm

Explain why a $\phi^4$ counterterm can cancel a divergent constant in the four-point vertex but cannot cancel a finite term such as

$$
\ln\frac{m^2-x(1-x)s-i\epsilon}{\mu^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The counterterm operator is local:

$$
-
\frac{\delta\lambda}{4!}\phi^4.
$$

Its momentum-space vertex is a constant:

$$
-i\delta\lambda.
$$

Therefore it can cancel only a local polynomial contribution to the four-point vertex. A divergent constant has exactly this form.

The logarithm depends non-polynomially on the external invariant $s$ and has branch-cut structure when thresholds are crossed. No local $\phi^4$ counterterm can reproduce that nonlocal dependence. The logarithm is part of the finite momentum dependence of the renormalized amplitude.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§16–20 and §§27–28, for vertex corrections, all-orders perturbation theory, and scheme dependence.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 15–16, 23, 25, and 50, for coupling renormalization, counterterms, and RG logic.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12 and Vol. II, ch. 18, for renormalization and running couplings in general QFT and gauge theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 19–23, for counterterms, renormalized perturbation theory, and beta functions in practical calculations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for coupling renormalization, MS, and RG functions.

## Version history

- **2026-06-12:** Initial polished draft. Added scalar coupling-counterterm conventions, one-loop $\phi^4$ example, beta-function extraction, momentum-subtraction definitions, scheme-dependence discussion, gauge/Yukawa preview, solved exercises, and a compact coupling-renormalization map figure.
