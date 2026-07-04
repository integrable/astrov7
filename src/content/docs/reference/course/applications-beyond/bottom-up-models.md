---
title: "Bottom-Up Models"
description: "How to build and read bottom-up holographic models responsibly, with emphasis on symmetries, effective bulk actions, observables, consistency checks, and model dependence."
sidebar:
  order: 110
---

The cleanest examples of AdS/CFT come from string theory. They give an exact microscopic pair: a specific quantum field theory and a specific quantum theory of gravity or strings in an asymptotically AdS spacetime. Bottom-up holography is different. It starts from the opposite direction: choose an effective bulk theory whose fields and symmetries are designed to capture some sector of a strongly coupled quantum system, then use the AdS/CFT dictionary as a computational engine.

This is both powerful and dangerous.

It is powerful because many robust holographic lessons do not depend on the microscopic details of $\text{AdS}_5\times S^5$. A black-brane horizon, a conserved current, a scalar order parameter, a relevant deformation, or an IR scaling region can be studied in a relatively small gravitational model. It is dangerous because writing down a bulk action is not the same thing as proving that a consistent, unitary, ultraviolet-complete boundary theory exists.

A good bottom-up model is not a magic dual of the real world. It is a controlled effective laboratory.

## Why this matters

Many of the most widely used holographic models in QCD-like physics and condensed-matter-inspired holography are bottom-up models. Examples include hard-wall and soft-wall AdS/QCD, Einstein–Maxwell–dilaton models, axion models of momentum relaxation, holographic superconductors, probe-fermion spectral functions, and phenomenological models of dense matter.

These models are useful because they let us ask questions such as: what does a strongly coupled plasma with a gravity dual generically do, which transport coefficients are controlled mainly by horizon regularity, how a conserved charge density reorganizes the IR degrees of freedom, what kinds of phases appear when a charged scalar becomes unstable, and which signatures are robust rather than artifacts of a chosen action.

But the right attitude is not “this model is QCD” or “this model is a strange metal.” The right attitude is:

> This model encodes a set of symmetries, degrees of freedom, scales, and boundary conditions. Its predictions are meaningful to the extent that they are insensitive to irrelevant modeling choices and compatible with holographic consistency.

That sentence is the whole page in miniature.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A bottom-up holographic model-building workflow: boundary target, bulk effective model, observables, UV data, IR data, consistency checks, and calibration.](/figures/course/bottom-up-models.svg)

<figcaption>

A bottom-up model is an effective bulk theory constrained by boundary symmetries, UV data, IR or horizon conditions, and consistency checks. It may be very useful without being a known UV-complete string construction.

</figcaption>
</figure>

## Top-down versus bottom-up

A **top-down model** begins with a known string or M-theory compactification. The boundary theory, the bulk field content, the action, the charge quantization, and the relation between parameters are inherited from the microscopic construction.

A **bottom-up model** begins with an effective bulk action. The model builder chooses fields, interactions, potentials, and boundary conditions because they capture desired features of a target class of field theories.

The contrast is not “rigorous versus useless.” It is more subtle.

| Feature | Top-down model | Bottom-up model |
|---|---|---|
| Microscopic dual | known, at least in principle | often unknown |
| Bulk field content | fixed by compactification/truncation | chosen phenomenologically |
| Parameters | constrained by fluxes and string data | fitted, scanned, or constrained by physics |
| UV completion | inherited from string/M-theory | not automatic |
| Flexibility | limited | high |
| Best use | exact examples, protected sectors, controlled limits | universality, phenomenology, mechanism studies |

Top-down models can be too rigid for phenomenological purposes. Bottom-up models can be too flexible. The art is to gain flexibility without losing the discipline of the dictionary.

## The minimal bottom-up grammar

A bottom-up model usually specifies four ingredients.

First, one chooses an asymptotically AdS background or an action that admits such backgrounds. The asymptotic region fixes the UV interpretation. If the metric approaches

$$
ds^2 \sim \frac{L^2}{z^2}\left(dz^2 + g_{(0)ij}(x)dx^i dx^j\right),
\qquad z\to 0,
$$

then the boundary theory is interpreted as living on the conformal class of $g_{(0)ij}$.

Second, one chooses bulk fields dual to important boundary operators. Typical examples are:

| Boundary structure | Bulk ingredient |
|---|---|
| stress tensor $T_{ij}$ | metric $g_{MN}$ |
| conserved current $J^i$ | gauge field $A_M$ |
| scalar operator $\mathcal O$ | scalar field $\phi$ |
| explicit breaking by source $J$ | non-normalizable mode of $\phi$ |
| spontaneous order | normalizable mode with zero source |
| momentum relaxation | scalar profiles, lattices, massive gravity, or axions |
| flavor sector | probe branes or bulk flavor gauge fields |

Third, one writes an effective action. A very common finite-density template is

$$
S = \frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left[
R
-\frac12(\partial \phi)^2
-V(\phi)
-\frac{Z(\phi)}4 F_{MN}F^{MN}
\right]
+S_{\rm bdy}.
$$

Here $V(\phi)$ controls the scalar potential and possible RG flow, while $Z(\phi)$ controls the effective gauge coupling. In holographic superconductors one adds a charged scalar,

$$
S_{\psi}
=
-\int d^{d+1}x\sqrt{-g}
\left(
|D\psi|^2 + m^2|\psi|^2 + \cdots
\right),
\qquad
D_M\psi=(\nabla_M-iqA_M)\psi .
$$

In simple AdS/QCD models one introduces flavor gauge fields and a scalar dual to the chiral condensate. In linear-axion models one introduces massless scalars with profiles such as

$$
\chi_I = k x_I,
$$

which break translations while preserving homogeneous bulk ordinary differential equations.

Fourth, one defines boundary and IR conditions. Near the AdS boundary, fields are expanded into sources and responses. In the interior, one imposes regularity, infalling conditions, smooth cap-off conditions, or a horizon ensemble.

The model is then used exactly like any other holographic setup: solve bulk equations, renormalize the on-shell action, vary with respect to sources, and extract observables.

## What is being modeled?

A bottom-up model should have a target. The target need not be a real material or QCD itself; it can be a universality class or a mechanism. The target determines what counts as success.

A model of a strongly coupled plasma might aim to reproduce an equation of state, speed of sound, viscosity, charge diffusion, or quasinormal spectrum. A model of chiral symmetry breaking might aim to reproduce pion physics, vector meson spectra, and current correlators. A model of finite-density criticality might aim to expose how an AdS$_2$ throat controls low-frequency response.

The most common targets are symmetry targets, operator targets, IR targets, and observable targets.

### Symmetry targets

These ask what happens if a quantum system has a stress tensor, a global $U(1)$ current, an order parameter, translations, rotations, parity, or time-reversal symmetry.

In holography, continuous global symmetries become bulk gauge symmetries. If the boundary theory has a conserved current $J^i$, the bulk has a gauge field $A_M$ with near-boundary expansion schematically

$$
A_i(z,x) = a_i(x) + z^{d-2} b_i(x)+\cdots,
$$

where $a_i$ sources $J^i$ and $b_i$ is related to $\langle J^i\rangle$.

### Operator targets

These ask what the important operators are in the low-energy or long-distance problem. For a scalar operator of dimension $\Delta$, the mass is fixed near the AdS boundary by

$$
m^2L^2=\Delta(\Delta-d).
$$

This relation is not optional. A bottom-up model may choose the scalar potential freely in the interior, but the UV mass determines the source dimension. A model that claims to describe a deformation by a dimension-$\Delta$ operator must get this asymptotic mass right.

### IR targets

These ask what kind of low-energy physics should emerge. Common IR geometries include an AdS$_{d+1}$ region corresponding to an IR CFT, a capped geometry suggesting a mass gap, an AdS$_2\times \mathbb R^{d-1}$ throat suggesting semi-local criticality, a Lifshitz or hyperscaling-violating geometry suggesting anisotropic scaling, and a black-brane horizon corresponding to a thermal state.

A bottom-up model is often judged by whether its IR endpoint is physically sensible, stable, and compatible with the desired phase.

### Observable targets

These ask which quantities will be compared across theories or to data. Examples include

$$
G_R^{JJ}(\omega,k),
\qquad
\sigma(\omega),
\qquad
s(T),
\qquad
\eta/s,
\qquad
\chi = \frac{\partial \rho}{\partial \mu},
\qquad
\langle \mathcal O\rangle(T,\mu).
$$

A model is more trustworthy when it predicts several observables after being calibrated to only a few inputs.

## Effective field theory in the bulk

Bottom-up holography is best understood as effective field theory in curved spacetime, with the AdS boundary conditions imposing a field-theory interpretation.

For example, suppose we write

$$
S_{\rm eff}
=
\frac{1}{16\pi G_{d+1}}\int d^{d+1}x\sqrt{-g}
\left[
R+\frac{d(d-1)}{L^2}
-\frac14 F^2
+\alpha L^2 (F^2)^2
+\beta L^2 R_{MNRS}R^{MNRS}
+\cdots
\right].
$$

This is an expansion in derivatives and fields. The coefficients $\alpha$, $\beta$, and their friends are not arbitrary if the model is to be UV-completable. In a true string compactification, higher-derivative terms are constrained by unitarity, causality, supersymmetry, charge quantization, and the spectrum of massive states.

In bottom-up work, one often truncates the action and studies a regime where the neglected terms are assumed to be small. This is legitimate as an effective approximation, but the regime of validity should be stated.

A useful diagnostic is

$$
\frac{\text{correction}}{\text{leading term}} \ll 1.
$$

If a model depends sensitively on large higher-derivative coefficients, strong curvature, or Planck-scale physics, it is no longer a controlled classical bulk calculation.

## A responsible model-building workflow

A disciplined bottom-up calculation usually follows this chain.

### Step 1: State the boundary problem

Do not begin with the action. Begin with the physics.

What are the global symmetries? Is the state thermal, finite density, disordered, confining, superconducting, or critical? Which operators are important? Which observables are supposed to be universal?

For example, a finite-density translationally invariant plasma with a conserved $U(1)$ current minimally needs $g_{MN}$ and $A_M$. A model of spontaneous breaking of that $U(1)$ needs a charged scalar. A model of explicit translation breaking needs additional structure.

### Step 2: Choose the bulk fields by the dictionary

The field content should be justified by boundary operators, not by convenience alone.

A scalar field is dual to a scalar operator. A gauge field is dual to a conserved current. A metric fluctuation is dual to the stress tensor. A bulk spinor is dual to a fermionic operator.

Extra light bulk fields mean extra light single-trace operators. If these operators have no interpretation in the target problem, the model may still be useful, but the extra sector should be acknowledged.

### Step 3: Fix the UV asymptotics

The UV asymptotic form is where the dictionary is most rigid. If the UV is AdS, masses and falloffs determine dimensions. For a scalar,

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+z^\Delta \phi_{(2\Delta-d)}(x)+\cdots .
$$

The source dimension is $d-\Delta$. If the scalar is used to represent a quark mass, a condensate, a lattice source, or an order parameter, that assignment has to be consistent with its UV dimension and boundary conditions.

### Step 4: Choose the ensemble

In finite-density holography, the ensemble matters. Fixing $A_t$ at the boundary fixes the chemical potential $\mu$ and describes a grand-canonical ensemble. Fixing radial electric flux fixes the charge density $\rho$ and describes a canonical ensemble.

The two are related by a Legendre transform. Mixing them silently is a common source of wrong thermodynamics.

### Step 5: Solve the background

One solves classical equations of motion for a background geometry and matter fields. For a homogeneous black brane, this often reduces to ordinary differential equations in the radial coordinate.

A standard ansatz might be

$$
ds^2 = -D(r)dt^2 + B(r)dr^2 + C(r)d\vec x^2,
\qquad
A=A_t(r)dt,
\qquad
\phi=\phi(r).
$$

The UV solution fixes sources and expectation values. The IR solution imposes regularity at a horizon or cap-off. Thermodynamics then follows from the renormalized on-shell action or from horizon data plus the first law.

### Step 6: Study perturbations

Observables usually come from linearized perturbations around the background. For conductivity, perturb $A_x(r)e^{-i\omega t}$. For shear viscosity, perturb $h^x{}_y(r)e^{-i\omega t}$. For scalar susceptibilities, perturb the scalar.

The retarded prescription imposes infalling boundary conditions at the horizon and reads the response/source ratio at the boundary:

$$
G_R(\omega,k)
\sim
\frac{\text{renormalized response}}{\text{source}}.
$$

### Step 7: Renormalize and check Ward identities

Bottom-up models need holographic renormalization just as top-down models do. The counterterms may be simpler, but they are not optional. A good calculation checks

$$
\nabla_i \langle T^{ij}\rangle
=
F^{j}{}_{i}\langle J^i\rangle
+\sum_a \langle\mathcal O_a\rangle\nabla^j J_a,
$$

and

$$
\nabla_i\langle J^i\rangle=0
$$

unless the model includes anomalies, explicit symmetry breaking, or charged sources.

### Step 8: Identify robust predictions

A bottom-up prediction is strongest if it survives deformations of irrelevant details. For example, the ratio $\eta/s=1/(4\pi)$ is robust across a large class of two-derivative Einstein gravity models because the shear graviton action near the horizon has a universal form. By contrast, the detailed shape of an optical conductivity curve may depend strongly on the choice of potential, charge coupling, translation-breaking sector, and boundary conditions.

The more knobs a model has, the more important it is to ask which conclusions are stable.

## Example: hard-wall and soft-wall AdS/QCD

AdS/QCD models are among the cleanest examples of bottom-up holography. They are not derived from QCD. Instead, they encode some large-$N$ and chiral features of QCD into a five-dimensional model.

A hard-wall model begins with a slice of AdS$_5$,

$$
0<z<z_m,
\qquad
 ds^2=\frac{L^2}{z^2}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
$$

where $z_m$ is an IR cutoff. The cutoff produces a discrete spectrum. Flavor symmetries are modeled by five-dimensional gauge fields,

$$
SU(N_f)_L\times SU(N_f)_R
\quad\longrightarrow\quad
A^L_M,\ A^R_M,
$$

and chiral symmetry breaking is modeled by a scalar $X$ transforming bifundamentally under the flavor group. Near the boundary,

$$
X(z) \sim m_q z + \sigma z^3,
$$

where $m_q$ is interpreted as a quark-mass source and $\sigma$ as a chiral condensate.

A soft-wall model replaces the sharp cutoff with a background profile, often written as a dilaton factor such as

$$
e^{-\Phi(z)},
\qquad
\Phi(z)\sim \kappa^2 z^2.
$$

This can produce approximately linear Regge trajectories,

$$
m_n^2 \sim n,
$$

which the simplest hard wall does not naturally produce.

The success of such models is phenomenological: they organize hadronic observables in a small number of geometric parameters. The limitation is equally important: the five-dimensional model is not known to be the exact large-$N$ dual of QCD.

## Example: holographic superconductors

The simplest holographic superconductor uses Einstein–Maxwell theory coupled to a charged scalar:

$$
S=\int d^{d+1}x\sqrt{-g}
\left[
\frac{1}{16\pi G_{d+1}}
\left(R+\frac{d(d-1)}{L^2}\right)
-\frac14 F^2
-|D\psi|^2
-m^2|\psi|^2
\right].
$$

At high temperature, the charged black brane can have $\psi=0$. At low temperature, the effective mass of $\psi$ near the horizon can drop below the relevant stability bound, producing scalar hair. In the boundary theory, this corresponds to spontaneous breaking of a global $U(1)$ symmetry and a nonzero expectation value

$$
\langle \mathcal O\rangle \neq 0
$$

with zero source.

This model teaches a robust mechanism: charged horizons can become unstable to charged condensates. But the simplest model does not automatically describe an electromagnetic superconductor in the lab, because the boundary $U(1)$ is usually global. To get an actual dynamical photon on the boundary, one must add or weakly gauge a boundary electromagnetic field.

## Example: holographic momentum relaxation

In a translationally invariant finite-density system, the electric conductivity contains a zero-frequency delta function. Momentum cannot decay, so an applied electric field accelerates the entire system.

Bottom-up models often break translations explicitly. A popular homogeneous choice is the linear-axion model,

$$
\chi_I=k x_I,
\qquad I=1,\ldots,d-1,
$$

with scalar action

$$
S_\chi=-\frac12\sum_I\int d^{d+1}x\sqrt{-g}\,(\partial\chi_I)^2.
$$

The scalar profiles break translations but preserve homogeneity in the bulk equations. This makes DC conductivity analytically computable from horizon data in many cases.

The model is useful because it isolates the role of momentum relaxation. But it is not a microscopic lattice unless one can explain what operator is being sourced, how the source enters the boundary theory, and whether the homogeneous approximation captures the desired physical regime.

## Universal versus model-dependent results

Bottom-up holography is most convincing when it identifies universal structures. A result is often robust when it follows from symmetry, conservation laws, horizon regularity, near-boundary asymptotics, thermodynamic identities, or the existence of a controlled scaling regime.

A result is more model-dependent when it depends on detailed scalar potentials $V(\phi)$, arbitrary functions such as $Z(\phi)$, large higher-derivative couplings, ad hoc IR boundary conditions, fitting many parameters to few observables, or assuming a light field with no boundary interpretation.

The difference is not binary. One can often separate robust mechanisms from detailed numbers. For example, the existence of a superconducting instability may be robust, while the precise value of $T_c/\mu$ is model-dependent.

## Consistency checks

A bottom-up model should pass at least the following checks.

### Correct variational principle

The action, boundary terms, and boundary conditions must define a well-posed variational problem. If the source is fixed, the variation should take the form

$$
\delta S_{\rm ren}
=
\int d^dx\sqrt{-g_{(0)}}
\left(
\frac12\langle T^{ij}\rangle\delta g_{(0)ij}
+\langle J^i\rangle\delta A_{(0)i}
+\sum_a \langle\mathcal O_a\rangle\delta J_a
\right).
$$

### Finite renormalized observables

The on-shell action and one-point functions should be renormalized. Divergent coefficients in a near-boundary expansion are not physical vevs.

### Ward identities

Gauge invariance, diffeomorphism invariance, and Weyl transformations imply Ward identities. Violating them usually means the sources, counterterms, or boundary conditions are inconsistent.

### Thermodynamic consistency

The free energy, charge density, entropy, and energy should obey the first law,

$$
d\epsilon = Tds + \mu d\rho + \cdots,
$$

with extra terms for additional sources. If a numerically generated solution violates the first law, something is wrong or the ensemble has been misidentified.

### Stability

A background should be checked for tachyonic, gradient, and thermodynamic instabilities. A solution that exists is not automatically a stable phase.

### Causality and positivity

Higher-derivative terms can change propagation speeds, spectral positivity, or boundary causality. A bottom-up model with arbitrary higher-derivative couplings should not be trusted beyond the regime in which those corrections are small.

### Large-$N$ consistency

A classical bulk model assumes a large number of boundary degrees of freedom. If the intended target has no large-$N$ analogue, one should interpret the model as a qualitative mechanism rather than a literal dual.

## What bottom-up models can teach

Bottom-up models are especially good at teaching mechanisms. Some examples:

- horizons encode dissipation and thermal response;
- gauge fields encode finite density and charge diffusion;
- charged scalar hair encodes spontaneous symmetry breaking;
- IR geometries encode scaling exponents;
- translation breaking controls DC transport;
- bulk mass and charge determine operator dimension and charge;
- extremal horizons can produce emergent AdS$_2$ physics;
- entanglement surfaces diagnose confinement-like transitions and effective degrees of freedom.

They also teach computational discipline. A student who masters a bottom-up calculation often understands the practical dictionary better than a student who has only read top-down slogans.

## What bottom-up models cannot do by themselves

A bottom-up model cannot, by itself, prove that a particular real-world material has a gravity dual, that QCD is exactly described by a five-dimensional classical geometry, that arbitrary bulk potentials define consistent quantum gravity theories, that fitted parameters are fundamental, that all features of a computed correlator are universal, or that the model is valid outside its controlled regime.

The dangerous move is to take a useful analogy and silently promote it into an exact duality.

Bottom-up models deserve neither worship nor dismissal. They deserve careful use.

## Dictionary checkpoint

The bottom-up dictionary is the same source-response dictionary used throughout the course, but with an extra layer of humility:

| Bulk ingredient | Boundary interpretation | What must be checked |
|---|---|---|
| asymptotic AdS metric | UV CFT or near-CFT structure | correct boundary dimension and sources |
| scalar mass $m^2$ | operator dimension $\Delta$ | $m^2L^2=\Delta(\Delta-d)$ |
| scalar source | coupling or deformation | explicit versus spontaneous breaking |
| bulk gauge field | global current | boundary conditions and ensemble |
| horizon | thermal state and dissipation | regularity, temperature, entropy |
| IR wall or cap | mass gap or confinement-like scale | boundary condition, stability |
| higher-derivative term | finite-gap or finite-coupling correction | causality, perturbative control |
| fitted potential | phenomenological input | robustness under deformations |

A top-down model inherits consistency from string theory. A bottom-up model must earn consistency one check at a time.

## Common confusions

### “If the model is asymptotically AdS, it has a CFT dual.”

Not necessarily. Asymptotic AdS behavior is necessary for the standard UV dictionary, but it is not sufficient to prove a complete, unitary, UV-complete CFT dual. The interior, spectrum, interactions, boundary conditions, and quantum consistency all matter.

### “Bottom-up means arbitrary.”

No. Bottom-up models are constrained by symmetry, the variational principle, holographic renormalization, Ward identities, thermodynamics, stability, and causality. Good bottom-up work is not arbitrary; it is disciplined effective theory.

### “Fitting data proves the model.”

A flexible model may fit data for many reasons. The stronger test is whether it predicts new observables, explains robust mechanisms, or shows universality under changes of irrelevant details.

### “A hard wall is a confining geometry.”

A hard wall can model a mass gap and a discrete spectrum, but it is imposed by hand. A smooth top-down confining geometry has dynamical IR structure. The hard wall is a useful toy model, not a derivation of confinement.

### “The boundary $U(1)$ in a holographic superconductor is automatically electromagnetism.”

In standard AdS/CFT, a bulk gauge field corresponds to a conserved global boundary current. The leading boundary value of $A_i$ is a source for that current. The boundary photon is not automatically dynamical.

## Exercises

### Exercise 1: Dimension from a chosen scalar mass

A bottom-up model in AdS$_5$ contains a scalar with $m^2L^2=-3$. What boundary dimensions are allowed by the scalar mass-dimension relation?

<details>
<summary><strong>Solution</strong></summary>

For AdS$_{d+1}$ with $d=4$,

$$
m^2L^2=\Delta(\Delta-4).
$$

Setting $m^2L^2=-3$ gives

$$
\Delta(\Delta-4)=-3,
$$

or

$$
\Delta^2-4\Delta+3=0.
$$

Thus

$$
\Delta=1
\qquad\text{or}\qquad
\Delta=3.
$$

Both roots are above the BF bound. In many AdS/QCD applications, the $\Delta=3$ root is used for a quark-bilinear-like operator $\bar q q$.

</details>

### Exercise 2: Why does translation invariance produce a delta function in conductivity?

Explain why a finite-density system with exact translation invariance generically has a zero-frequency delta function in $\mathrm{Re}\,\sigma(\omega)$.

<details>
<summary><strong>Solution</strong></summary>

At finite charge density, the electric current usually overlaps with the conserved momentum. If translations are exact, momentum cannot decay. An applied electric field continuously accelerates the charged fluid, so the DC conductivity is infinite.

In linear response, infinite DC conductivity appears as

$$
\mathrm{Re}\,\sigma(\omega)
\supset
\pi K\delta(\omega),
$$

with a corresponding pole in the imaginary part,

$$
\mathrm{Im}\,\sigma(\omega)
\sim
\frac{K}{\omega}.
$$

Bottom-up momentum-relaxing models break translations so that momentum can decay and the DC conductivity becomes finite.

</details>

### Exercise 3: What does a bulk gauge field mean?

In a bottom-up model, a bulk Maxwell field $A_M$ is introduced. Does this mean the boundary theory contains a dynamical photon?

<details>
<summary><strong>Solution</strong></summary>

No, not in the standard Dirichlet AdS/CFT dictionary. A bulk gauge field is dual to a conserved global current $J^i$ in the boundary theory. The leading boundary value of $A_i$ is a source for this current.

To make the boundary gauge field dynamical, one must change the boundary problem: for example, add a boundary Maxwell term or impose mixed boundary conditions in a suitable dimension. The default bulk Maxwell field represents a global symmetry, not boundary electromagnetism.

</details>

### Exercise 4: Robust versus model-dependent

A bottom-up model predicts that a charged scalar condenses below $T_c$. Which part of this statement is likely to be robust, and which part is likely to be model-dependent?

<details>
<summary><strong>Solution</strong></summary>

The robust part is the mechanism: at finite density, the gauge field and near-horizon geometry can make a charged scalar effectively unstable, leading to a condensate when the source is set to zero.

The model-dependent parts include the numerical value of $T_c$, the detailed optical conductivity curve, the precise condensate amplitude, and the order of the transition. These depend on the scalar mass, charge, potential, backreaction, higher-derivative terms, and other details of the model.

</details>

## Further reading

- J. Erlich, E. Katz, D. T. Son, and M. A. Stephanov, [QCD and a Holographic Model of Hadrons](https://arxiv.org/abs/hep-ph/0501128).
- L. Da Rold and A. Pomarol, [Chiral Symmetry Breaking from Five Dimensional Spaces](https://arxiv.org/abs/hep-ph/0501218).
- A. Karch, E. Katz, D. T. Son, and M. A. Stephanov, [Linear Confinement and AdS/QCD](https://arxiv.org/abs/hep-ph/0602229).
- S. A. Hartnoll, [Lectures on Holographic Methods for Condensed Matter Physics](https://arxiv.org/abs/0903.3246).
- J. McGreevy, [Holographic Duality with a View Toward Many-Body Physics](https://arxiv.org/abs/0909.0518).
- S. S. Gubser and A. Nellore, [Mimicking the QCD Equation of State with a Dual Black Hole](https://arxiv.org/abs/0804.0434).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
