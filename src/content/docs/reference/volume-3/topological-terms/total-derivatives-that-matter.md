---
title: "Total Derivatives That Matter"
description: "Explains when total derivatives and locally exact terms change a quantum field theory through boundaries, topology, patching, large transformations, and path-integral phases."
sidebar:
  label: "Total Derivatives That Matter"
  order: 2
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry; Srednicki §§93–94; Polyakov; Zee; Altland–Simons Ch. 8; standard references on theta terms, boundary terms, Chern–Simons forms, and Wess–Zumino terms."
topics:
  - total derivatives
  - boundary terms
  - topological terms
  - theta terms
  - large gauge transformations
  - Chern Simons forms
  - variational principles
canonicalTopics:
  - total-derivatives-that-matter
  - boundary-terms
  - topological-terms
  - large-gauge-transformations
  - topological-sectors
researchStatus:
  established:
    - "A locally total-derivative term can be physically meaningful in quantum field theory when the spacetime has boundary, the fields are not globally represented by one patch, the path integral sums over distinct topological sectors, or the coefficient is constrained by large transformations."
    - "The phrase 'total derivative' is therefore a local statement about a density, not by itself a proof that the term is physically irrelevant."
  active:
    - "Modern applications refine these statements using generalized backgrounds, global-form data, spin and Pin structures, boundary conditions, edge modes, and relative QFT language."
---

## Summary

A total derivative is often the first term students are taught to throw away. In ordinary variational calculus, if

$$
\mathcal L\longrightarrow \mathcal L+\partial_\mu K^\mu,
$$

then the action changes by

$$
\Delta S=\int_X d^dx\,\partial_\mu K^\mu
=\int_{\partial X} d\Sigma_\mu\,K^\mu,
$$

and this boundary term does not affect the Euler–Lagrange equations when the boundary variation is fixed. That statement is correct, useful, and dangerously incomplete.

In QFT, a locally total derivative can change the theory. It can assign phases to disconnected topological sectors, change the canonical symplectic potential, generate edge charges, shift contact terms, modify boundary conditions, encode anomaly inflow, or fail to be the derivative of a globally defined object. The slogan is:

$$
\text{total derivative locally}\;\not\Rightarrow\;\text{irrelevant quantum mechanically}.
$$

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing how a locally total derivative can become a boundary term, a patching contribution, or a topological sector phase.](/figures/symmetry-anomalies-topology/total-derivative-global-effects.svg)

<figcaption>

A local total derivative has three common fates. If the potential is globally defined and boundary data are fixed, it may be harmless. If there is a boundary, it becomes boundary dynamics or boundary data. If the potential exists only patchwise, or if the path integral sums over sectors, it can define a quantized phase.

</figcaption>
</figure>

This page is the cleanup crew for the phrase “up to a total derivative.” The phrase is allowed only after one has checked the boundary, topology, bundle, and quantum-phase data.

## Prerequisites

You should know [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), the basic distinction between background and dynamical fields from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), and the current-improvement discussion in [Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/). Differential-form notation is used freely.

We use the volume convention

$$
F=dA-iA\wedge A,
$$

for a gauge connection written with Hermitian generators. When comparing to sources with anti-Hermitian generators, signs and factors of $i$ move between $A$, $F$, and the Chern–Simons form. That is convention, not physics.

## Core idea

The local statement

$$
\omega_d=d\alpha_{d-1}
$$

has several hidden assumptions. It says that a $d$-form density $\omega_d$ is exact in some local description. It does not say that $\alpha_{d-1}$ is globally defined, gauge invariant, single valued, or compatible with the boundary conditions. It also does not say that the integral of $\omega_d$ over a closed spacetime vanishes, because the field configuration may be a map or bundle with nontrivial patching data.

A useful diagnostic is this table.

| Local statement | Extra question | Possible physical effect |
|---|---|---|
| $\omega_d=d\alpha_{d-1}$ | Is $\alpha_{d-1}$ global? | Quantized periods and theta phases |
| $\int_X d\alpha=\int_{\partial X}\alpha$ | Is $\partial X$ empty? | Boundary action, edge modes, anomaly inflow |
| $\delta\int_X d\alpha$ is a boundary variation | Which boundary data are fixed? | Different variational principle or canonical structure |
| $\omega_d$ is a total derivative in one patch | What happens under large transformations? | Coupling quantization or periodicity |
| $d\omega_d=0$ | Is $\omega_d$ exact as a global differential character? | Distinct topological actions |

The “ordinary” local equations of motion see only the bulk variation. The quantum theory sees the path integral measure, the allowed configuration space, boundary conditions, and the phase $e^{iS}$.

## Setup and conventions

Let $X_d$ be the spacetime manifold. In Lorentzian signature the path integral weight is $e^{iS}$; in Euclidean signature one often writes $e^{-S_E}$, but topological theta-like terms usually remain imaginary in $S_E$ so that they still contribute phases. We will often write formulas in differential forms, where a total derivative is an exterior derivative:

$$
S_{\mathrm{td}}=c\int_{X_d} d\alpha_{d-1}.
$$

If $\alpha_{d-1}$ is globally defined, Stokes’ theorem gives

$$
S_{\mathrm{td}}=c\int_{\partial X_d}\alpha_{d-1}.
$$

If $\partial X_d=\varnothing$, this vanishes. But the condition “$\alpha_{d-1}$ is globally defined” is doing real work. For gauge fields, sigma-model maps, and defects, it is often false. Locally exact forms can represent globally nontrivial cohomology classes once patching data are included.

A slightly more invariant way to say this is that many topological terms are not just ordinary differential forms. They are better viewed as differential cohomology classes, cocycles, or exponentiated actions. On a first pass, you do not need that formalism. You only need the operational rule:

:::note[Operational rule]
Before discarding a total derivative, check the boundary, patching, singularities, large transformations, and whether $e^{iS}$ is single valued on the allowed configuration space.
:::

## Classical equations versus quantum phases

For a variation with compact support in the interior of $X_d$,

$$
\delta S_{\mathrm{td}}
=c\int_{X_d}d\,\delta\alpha_{d-1}
=c\int_{\partial X_d}\delta\alpha_{d-1}.
$$

Thus $S_{\mathrm{td}}$ does not change the local Euler–Lagrange equations. This is the source of the useful habit of ignoring total derivatives in local classical field theory.

The path integral is more refined. Suppose the configuration space decomposes into components $\mathcal C_Q$ labeled by an integer $Q$ and

$$
\int_{X_d}\omega_d=Q\in\mathbb Z.
$$

Then

$$
Z(c)=\sum_{Q\in\mathbb Z}e^{icQ}Z_Q.
$$

No local equation of motion sees the coefficient $c$, but interference between sectors does. This is exactly the theta-term mechanism.

The simplest moral is:

$$
\text{local variation} \quad \text{and} \quad \text{global weighting of histories}
$$

are different questions.

## First example: a particle on a circle

Let $q(t)$ be an angular coordinate with

$$
q\sim q+2\pi.
$$

Consider the term

$$
S_\theta=\frac{\theta}{2\pi}\int dt\,\dot q.
$$

Locally this is the total derivative

$$
\frac{\theta}{2\pi}\dot q=\frac{d}{dt}\left(\frac{\theta q}{2\pi}\right).
$$

For a path with fixed endpoints in a single coordinate patch, it is just an endpoint phase. But in the quantum trace, paths are closed only modulo winding:

$$
q(\beta)=q(0)+2\pi n,
\qquad n\in\mathbb Z.
$$

Therefore

$$
S_\theta=\theta n.
$$

The partition function is a sum over winding sectors weighted by $e^{i\theta n}$. The local derivative was harmless only if one forgot that $q$ is an angle.

In the Hamiltonian description this same term shifts the canonical momentum:

$$
p=I\dot q+\frac{\theta}{2\pi}.
$$

The spectrum depends on $\theta$ through

$$
E_m(\theta)=\frac{1}{2I}\left(m-\frac{\theta}{2\pi}\right)^2,
\qquad m\in\mathbb Z,
$$

for the standard quantum rotor. A “mere” total derivative has changed the quantum spectrum.

## Second example: Yang–Mills instanton number

For a nonabelian gauge field in four Euclidean dimensions,

$$
Q=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)
$$

is the instanton number on a closed four-manifold, with the trace normalized as in the volume conventions. Locally,

$$
\operatorname{tr}(F\wedge F)=d\operatorname{CS}_3(A),
$$

where, with our Hermitian-generator convention,

$$
\operatorname{CS}_3(A)=\operatorname{tr}\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right).
$$

Here is the convention-sensitive point: $\operatorname{CS}_3(A)$ is not gauge invariant under large gauge transformations and is not a globally defined gauge-invariant three-form on an arbitrary bundle. The four-form $\operatorname{tr}(F\wedge F)$ is global and gauge invariant; the Chern–Simons form is a local potential for it.

Thus on closed $X_4$, the integral of $\operatorname{tr}(F\wedge F)$ need not vanish. It measures the topology of the gauge bundle. The theta term

$$
S_\theta=\frac{\theta}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)
$$

weights sectors by $e^{i\theta Q}$ even though the density is locally a total derivative.

This is the archetype of the whole page: a local derivative becomes global data because the local potential is not a single-valued globally gauge-invariant object.

## Boundary terms and variational principles

Even if a total derivative is globally exact, it may matter when $X_d$ has a boundary. The action does not define only equations of motion. It also defines a variational principle.

For a scalar field, integrating by parts gives

$$
\delta S=\int_X d^dx\,E(\phi)\delta\phi
+\int_{\partial X}d\Sigma_\mu\,\Theta^\mu(\phi,\delta\phi),
$$

where $E(\phi)=0$ is the bulk equation of motion and $\Theta^\mu$ is the symplectic-potential current. Adding a total derivative changes

$$
\Theta^\mu\longrightarrow \Theta^\mu+\delta K^\mu.
$$

If the boundary value of $\phi$ is fixed, this may not change anything. If the boundary value is dynamical, or if one wants Neumann, mixed, radiative, or asymptotic boundary conditions, it can change the canonical data.

This is not a technicality. Boundary terms decide which variables are fixed, which charges are integrable, what the edge symplectic form is, and whether a variational problem is well posed. The same local bulk equations can therefore support different quantum theories once boundary data are specified.

A familiar non-gauge example is adding a total time derivative in mechanics:

$$
L(q,\dot q,t)\longrightarrow L(q,\dot q,t)+\frac{dF(q,t)}{dt}.
$$

The equations of motion do not change, but the canonical momentum shifts by

$$
p_i\longrightarrow p_i+\frac{\partial F}{\partial q^i}.
$$

In quantum mechanics this is implemented by a boundary phase in the wavefunction. On simply connected configuration spaces this is often a harmless unitary redefinition. On multiply connected spaces it can become a physical theta parameter.

## Current improvements and contact terms

Total derivatives also appear in local operator definitions. If a current is shifted by

$$
J^\mu\longrightarrow J^\mu+\partial_\nu B^{[\nu\mu]},
$$

then

$$
\partial_\mu J^\mu
$$

is unchanged identically, because $B^{[\nu\mu]}$ is antisymmetric. On a closed spatial slice with suitable falloff, the charge

$$
Q=\int_\Sigma d\Sigma_\mu J^\mu
$$

is unchanged. But correlation functions involving $J^\mu(x)$ can change by derivative contact terms.

This is why total derivatives cannot be ignored in Ward-identity pages. They move local terms around. They can change the definition of the stress tensor, the local current, and the generating functional in background fields. They should be regarded as scheme data unless they are fixed by a normalization condition, background coupling, or boundary prescription.

The distinction is:

$$
\text{integrated conserved charge}\quad \neq\quad \text{local current operator as a distribution}.
$$

The former may be insensitive to an improvement; the latter often is not.

## Large transformations and coefficient quantization

A total derivative can also be meaningful because its integral changes by a quantized amount under a large transformation. The path integral only needs $e^{iS}$ to be invariant, not necessarily $S$ itself. Therefore a shift

$$
S\longrightarrow S+2\pi k,
\qquad k\in\mathbb Z,
$$

is invisible, while a generic real shift is not.

This is the origin of many quantization conditions. For a three-dimensional Chern–Simons action, the local density is built from a connection and resembles a total-derivative descendant of $\operatorname{tr}(F\wedge F)$ in one higher dimension. Under large gauge transformations, the action can shift by $2\pi$ times the level. Requiring $e^{iS}$ to be gauge invariant quantizes the level, with refinements depending on the gauge group, matter content, spin structure, and global form.

The same logic appears in Wess–Zumino terms. The action is often defined by extending fields into one higher dimension. Different extensions change the action by an integral over a closed cycle. The coefficient must be chosen so that the exponentiated action is independent of the extension.

## Singular configurations and defects

Another way total derivatives become physical is through singularities or defects. Stokes’ theorem applied to $X$ minus a small tubular neighborhood of a defect gives a boundary surrounding the defect. A local derivative then measures charge linked by that small boundary.

For example, magnetic monopoles, vortices, and instantons are often detected by integrals that can be written locally as derivatives away from the defect core. The nonzero answer comes from the fact that the field is not globally smooth and trivial on the whole space. The “missing” contribution is sitting at the patching locus, the defect boundary, or infinity.

This is a useful mental model:

$$
\text{topological charge} = \text{flux through a boundary you did not notice at first}.
$$

The boundary might be spatial infinity, a small sphere around a defect, a transition function between patches, or an auxiliary extension manifold.

## The hierarchy of harmlessness

When is a total derivative genuinely harmless? A good sufficient checklist is:

1. The total derivative is the derivative of a globally defined single-valued local functional.
2. The spacetime has no boundary, or the boundary contribution is fixed and physically irrelevant.
3. The allowed field configurations have no singularities, defects, or nontrivial patching that contribute.
4. The path integral does not sum over sectors distinguished by the integral of the density.
5. The term does not change the symplectic structure, charge definition, or source dependence one wants to keep fixed.
6. The exponentiated action remains invariant under all allowed small and large transformations.

If all six are true, the total derivative is probably safe to drop. If any one fails, pause. This is not paranoia; it is how theta terms, Chern–Simons terms, Wess–Zumino terms, edge modes, Berry phases, and anomaly inflow sneak into QFT.

## Common pitfalls

**Mistaking local exactness for global triviality.** The formula $\omega=d\alpha$ in one coordinate patch does not prove $\int_X\omega=0$ on a closed manifold. Gauge bundles and sigma-model targets are patched.

**Forgetting the exponentiated action.** A shift of $S$ by $2\pi\mathbb Z$ is harmless in Lorentzian quantum theory; a shift by a generic real number is not. Quantization conditions are conditions on $e^{iS}$.

**Throwing away boundary terms before specifying boundary conditions.** Different boundary terms correspond to different canonical data. Do not discard them before deciding what is fixed at the boundary.

**Confusing current improvements with zero.** Improvements may not change integrated charges, but they can change local current correlators and contact terms.

**Assuming perturbation theory sees everything.** Perturbation theory around a trivial field configuration often misses effects that live in disconnected sectors or at large field-space distance.

## Relations to other pages

- [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) is the canonical example of a locally total-derivative density that changes the path integral through sector phases.
- [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/) explains the extension-manifold version of the same principle.
- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) develops a case where large gauge transformations force coefficient quantization.
- [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) explains how total derivatives change Ward identities as distributions.
- [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/) explains why transformations disconnected from the identity cannot be ignored.
- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) uses boundary total derivatives as the mechanism by which a bulk variation cancels a boundary anomaly.

## Research status

The core lesson is established textbook QFT and geometry: locally exact densities can carry global, boundary, or quantum information. The modern research activity is in the refinements: how these terms depend on spin, Pin, global-form, higher-form, and differential-cohomology data; how edge modes and asymptotic symmetries should be organized; and how to phrase topological terms and anomalies in relative or symmetry-TFT language.

The safe practical stance is conservative. When a topological term is involved, define the exponentiated action on the full allowed configuration space, not just the infinitesimal Lagrangian density in one patch.

## Exercises

### Exercise 1: Endpoint phase for an ordinary total derivative

Let

$$
L'(q,\dot q,t)=L(q,\dot q,t)+\frac{dF(q,t)}{dt}.
$$

Show that the classical equations of motion are unchanged and that the quantum transition amplitude changes by an endpoint phase.

<details><summary><strong>Solution</strong></summary>

The action changes by

$$
S'[q]=S[q]+F(q_f,t_f)-F(q_i,t_i).
$$

The variation of the extra term is

$$
\delta F(q_f,t_f)-\delta F(q_i,t_i),
$$

which vanishes when the endpoints are fixed. Hence the Euler–Lagrange equations are unchanged.

In the path integral,

$$
K'(q_f,t_f;q_i,t_i)
=\int_{q_i}^{q_f}\mathcal Dq\,e^{iS'[q]}
=e^{iF(q_f,t_f)}K(q_f,t_f;q_i,t_i)e^{-iF(q_i,t_i)}.
$$

Thus the total derivative is an endpoint rephasing of states. On topologically simple configuration spaces this is usually harmless. On angular configuration spaces it can become a theta parameter.

</details>

### Exercise 2: Particle on a circle

For a quantum rotor with

$$
L=\frac{I}{2}\dot q^2+\frac{\theta}{2\pi}\dot q,
\qquad q\sim q+2\pi,
$$

show that closed Euclidean paths in the trace are weighted by $e^{i\theta n}$, where $n$ is the winding number.

<details><summary><strong>Solution</strong></summary>

A path contributing to the trace obeys

$$
q(\beta)=q(0)+2\pi n,
\qquad n\in\mathbb Z.
$$

Therefore

$$
\frac{1}{2\pi}\int_0^\beta d\tau\,\dot q
=\frac{q(\beta)-q(0)}{2\pi}=n.
$$

The theta term contributes

$$
S_\theta=\theta n,
$$

so the sector of winding $n$ is weighted by

$$
e^{iS_\theta}=e^{i\theta n}.
$$

The term is locally a derivative but globally measures winding.

</details>

### Exercise 3: Why a closed manifold is not enough

Suppose $X_4$ is closed and $A$ is a nonabelian gauge connection. Explain why the statement

$$
\operatorname{tr}(F\wedge F)=d\operatorname{CS}_3(A)
$$

does not imply

$$
\int_{X_4}\operatorname{tr}(F\wedge F)=0
$$

for arbitrary gauge bundles.

<details><summary><strong>Solution</strong></summary>

The formula with $\operatorname{CS}_3(A)$ is local. It holds in a gauge patch where the connection is represented by a one-form $A$. On a nontrivial bundle, there may be no globally defined $A$ on all of $X_4$ in one patch, and $\operatorname{CS}_3(A)$ is not a globally defined gauge-invariant three-form.

The four-form $\operatorname{tr}(F\wedge F)$ is global. Its integral can measure the second Chern class of the bundle:

$$
Q=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

under the standard normalization. The nonzero answer comes from patching data, not from a failure of the local identity.

</details>

### Exercise 4: Improvement and charge

Let

$$
J'^\mu=J^\mu+\partial_\nu B^{[\nu\mu]}.
$$

Assume a spatial slice $\Sigma$ has no boundary, or that fields fall off fast enough at infinity. Show that the charge generated by $J'^\mu$ equals the charge generated by $J^\mu$.

<details><summary><strong>Solution</strong></summary>

The charge difference is

$$
\Delta Q=\int_\Sigma d\Sigma_\mu\,\partial_\nu B^{[\nu\mu]}.
$$

For an equal-time slice this becomes a spatial divergence plus possible time-component bookkeeping. Under the stated assumptions it reduces to a boundary integral on $\partial\Sigma$:

$$
\Delta Q=\int_{\partial\Sigma}\cdots.
$$

If $\partial\Sigma=\varnothing$, or if the fields fall off so that the boundary integral vanishes, then $\Delta Q=0$. The local current operator can still differ by contact terms inside correlation functions.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “The Uses of Instantons,” for theta vacua and topological total-derivative effects.
- Mark Srednicki, *Quantum Field Theory*, §§93–94, for instantons, theta vacua, and the physical role of $F\wedge F$.
- A. M. Polyakov, *Gauge Fields and Strings*, for topology of gauge fields, instantons, compact gauge fields, and global effects.
- A. Zee, *Quantum Field Theory in a Nutshell*, for physically motivated examples of total derivatives, monopoles, sigma models, and topological terms.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for theta terms, Wess–Zumino terms, and Chern–Simons terms in matter-oriented QFT.
- Edward Witten, “Dyons of Charge $e\theta/2\pi$,” *Physics Letters B* **86** (1979), for the Witten effect.
- Edward Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* **223** (1983), for the global quantization logic behind Wess–Zumino–Witten terms.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
