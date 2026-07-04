---
title: "RG Flows and Domain Walls"
description: "How relevant deformations, running couplings, and changes of degrees of freedom are encoded by scalar profiles and domain-wall geometries in holography."
sidebar:
  order: 30
---

The canonical AdS/CFT example is conformal. Its vacuum geometry is exactly AdS, its boundary theory has no intrinsic scale, and the radial direction is tied to scale transformations. Real quantum field theories are rarely so rigid. They have masses, relevant deformations, condensates, confinement scales, symmetry breaking, crossovers, and sometimes new infrared fixed points.

Holography describes such physics by replacing exact AdS with an *asymptotically* AdS geometry. Near the boundary, the solution still looks like the ultraviolet CFT. Deeper in the bulk, scalar fields and the warp factor change. The geometry becomes a gravitational picture of renormalization group flow.

The central idea is:

$$
\text{relevant deformation of a UV CFT}
\quad \longleftrightarrow \quad
\text{bulk scalar profile in an asymptotically AdS domain wall}.
$$

The phrase “domain wall” here means a spacetime whose metric preserves $d$-dimensional Poincaré invariance along the field-theory directions while varying in the radial direction. It is not a wall in the boundary theory. It is the bulk geometry of a state or theory with scale dependence.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Holographic RG flow as a domain-wall geometry.](/figures/course/rg-flows-domain-walls.svg)

<figcaption>

A holographic RG flow. Near the boundary, the solution approaches an ultraviolet AdS region and is controlled by CFT data. A relevant source or vev turns on a scalar profile $\phi(u)$, and the warp factor $A(u)$ changes along the radial direction. The deep interior may approach another AdS region, giving an IR CFT, or end at a cap, wall, horizon, or singularity, signaling nonconformal IR physics.

</figcaption>
</figure>

## Why this matters

RG flows are the bridge between the pristine conformal examples and the physics one actually wants to model. They teach us how holography treats:

- relevant deformations of a CFT;
- spontaneous condensates and vacuum expectation values;
- flows from one fixed point to another;
- mass gaps and confinement-like infrared behavior;
- the loss of degrees of freedom along RG flow;
- bottom-up models where one engineers an infrared geometry.

They also prevent a common misunderstanding. Holography is not restricted to fixed points. Exact AdS is dual to a CFT vacuum or state, but asymptotically AdS spacetimes describe relevantly deformed theories, states with expectation values, finite-temperature states, finite-density states, and many other nonconformal situations.

## Field-theory setup: deforming a CFT

Start with a UV CFT in $d$ dimensions and perturb it by a scalar primary operator $\mathcal O$:

$$
S_{\rm QFT}
=
S_{\rm CFT}
+
\int d^d x\, J(x)\mathcal O(x).
$$

If $\mathcal O$ has scaling dimension $\Delta$, the source has engineering dimension

$$
[J]=d-\Delta.
$$

A relevant deformation has

$$
\Delta<d.
$$

Then $J$ introduces a scale. If $J$ is constant, a useful dimensionless coupling at energy scale $\mu$ is

$$
g(\mu)\sim J\,\mu^{\Delta-d}.
$$

For $\Delta<d$, this coupling becomes more important as $\mu$ decreases. The UV theory may flow to:

1. another CFT in the infrared;
2. a gapped theory;
3. a confining theory;
4. a theory with spontaneous symmetry breaking;
5. a singular or otherwise pathological endpoint.

Holographically, these possibilities are distinguished by the deep-interior behavior of the bulk geometry.

## Bulk setup: Einstein-scalar domain walls

The simplest holographic RG flows are described by Einstein gravity coupled to scalar fields:

$$
S
=
\frac{1}{2\kappa_{d+1}^2}
\int d^{d+1}x\sqrt{-g}
\left[
R
-
\frac12 G_{ab}(\phi)\partial_M\phi^a\partial^M\phi^b
-
V(\phi)
\right]
+
S_{\rm bdy}.
$$

For one scalar, set $G_{ab}=1$. A Poincaré-invariant domain wall has metric

$$
ds^2
=
du^2+e^{2A(u)}\eta_{ij}dx^i dx^j,
$$

with scalar profile

$$
\phi=\phi(u).
$$

The radial coordinate $u$ is convenient because constant-$u$ slices look like flat $d$-dimensional spacetime. Near an AdS boundary,

$$
A(u)\sim \frac{u}{L},
\qquad
u\to +\infty.
$$

In Poincaré coordinates, this is equivalent to

$$
z\sim L e^{-u/L},
\qquad
\mu\sim \frac{1}{z}\sim e^{u/L}.
$$

Thus increasing $u$ goes toward the ultraviolet, while moving inward toward smaller $u$ follows the RG flow toward the infrared.

## Critical points of the scalar potential are fixed points

A constant scalar solution $\phi=\phi_*$ is possible when

$$
\partial_\phi V(\phi_*)=0.
$$

If the potential at the critical point is negative,

$$
V(\phi_*)=-\frac{d(d-1)}{L_*^2},
$$

then the geometry is $\mathrm{AdS}_{d+1}$ with radius $L_*$. This is a holographic fixed point.

A flow from one critical point to another has the schematic form

$$
\mathrm{AdS}_{d+1}^{\rm UV}
\quad \longrightarrow \quad
\mathrm{domain\ wall}
\quad \longrightarrow \quad
\mathrm{AdS}_{d+1}^{\rm IR}.
$$

The UV and IR AdS radii encode the number of degrees of freedom. For Einstein gravity,

$$
c_{\rm eff}\sim \frac{L^{d-1}}{G_{d+1}}.
$$

So a flow between two AdS regions gives

$$
\frac{c_{\rm IR}}{c_{\rm UV}}
=
\left(\frac{L_{\rm IR}}{L_{\rm UV}}\right)^{d-1}
$$

up to convention-dependent normalizations of the central charge or sphere free energy.

## Near-boundary scalar behavior: source and response again

Near the UV AdS boundary, a scalar with mass

$$
m^2=V''(\phi_{\rm UV})
$$

has the asymptotic behavior

$$
\phi(z,x)
=
z^{d-\Delta}\phi_{(0)}(x)
+
\cdots
+
z^\Delta \phi_{(2\Delta-d)}(x)
+
\cdots,
$$

where

$$
m^2L^2=\Delta(\Delta-d).
$$

For a constant deformation,

$$
\phi_{(0)}=J.
$$

The coefficient of the normalizable falloff is related to the expectation value:

$$
\langle\mathcal O\rangle
\sim
(2\Delta-d)\phi_{(2\Delta-d)}
+
\text{local terms}.
$$

The local terms are precisely the terms fixed by holographic renormalization. Their detailed form depends on the operator dimension, the boundary dimension, and the scheme.

The distinction between source and response remains essential. A scalar profile in the bulk does not automatically mean the boundary theory has been deformed. It may also mean that the undeformed theory is in a state with a condensate.

## Source-driven flows versus vev-driven flows

There are two basic ways a scalar profile can appear.

### Source-driven flow

If the non-normalizable coefficient is nonzero,

$$
\phi_{(0)}\neq 0,
$$

then the Lagrangian has been deformed:

$$
S_{\rm CFT}\to S_{\rm CFT}+\int \phi_{(0)}\mathcal O.
$$

This is the cleanest holographic version of an RG flow. A relevant operator is turned on in the UV, and the theory evolves toward an IR endpoint.

### Vev-driven flow

If

$$
\phi_{(0)}=0,
\qquad
\langle\mathcal O\rangle\neq 0,
$$

then the microscopic Lagrangian is unchanged, but the state or vacuum has an expectation value. Such flows often describe spontaneous symmetry breaking, Coulomb-branch states, or moduli-space physics.

In practice, many geometries contain both source and vev data. The near-boundary expansion tells you what the UV field theory is, while the interior regularity condition often determines the vev as a function of the source.

## Einstein-scalar equations

For the action

$$
S
=
\frac{1}{2\kappa_{d+1}^2}
\int \sqrt{-g}\left(R-\frac12(\partial\phi)^2-V(\phi)\right),
$$

and the domain-wall ansatz

$$
ds^2=du^2+e^{2A(u)}\eta_{ij}dx^i dx^j,
\qquad
\phi=\phi(u),
$$

the equations of motion reduce to

$$
\phi''+dA'\phi'-\partial_\phi V=0,
$$

$$
A''=-\frac{1}{2(d-1)}(\phi')^2,
$$

and the constraint

$$
(A')^2
=
\frac{1}{d(d-1)}
\left(
\frac12(\phi')^2-V(\phi)
\right).
$$

The second equation is especially important. Since

$$
(\phi')^2\ge 0,
$$

we have

$$
A''\le 0.
$$

This inequality is the gravitational seed of a holographic $c$-theorem.

## Holographic beta functions

A rough but useful definition of the holographic beta function is

$$
\beta(\phi)
=
\frac{d\phi}{d\log\mu}.
$$

Since the local energy scale is tied to the warp factor,

$$
\log\mu\sim A(u),
$$

we define

$$
\beta(\phi)
=
\frac{d\phi}{dA}
=
\frac{\phi'(u)}{A'(u)}.
$$

Near a UV fixed point, the linearized scalar equation gives

$$
\phi(u)
\sim
J e^{-(d-\Delta)u/L}
+
\langle\mathcal O\rangle e^{-\Delta u/L}.
$$

For a source-driven flow, the leading behavior is

$$
\phi\sim J e^{-(d-\Delta)u/L}.
$$

Therefore

$$
\beta(\phi)
\sim
-(d-\Delta)\phi.
$$

This is the expected field-theory result: the linearized beta function of a relevant coupling begins with its engineering dimension.

There is a small convention trap here. If one uses $z$ instead of $u$, then $z$ increases toward the IR, while $\mu\sim 1/z$. Sign conventions for beta functions can therefore look different unless the energy-scale convention is stated explicitly.

## The holographic $c$-theorem

For a Poincaré-invariant Einstein-scalar domain wall, define

$$
a(u)
\propto
\frac{1}{[A'(u)]^{d-1}}.
$$

Using $A''\le 0$,

$$
\frac{da}{du}
\propto
-(d-1)\frac{A''}{[A']^d}
\ge 0
$$

provided $A'>0$. Since $u$ increases toward the UV, this says that $a$ increases toward the UV and therefore decreases toward the IR.

At an AdS fixed point, $A'=1/L_*$, so

$$
a_*\propto L_*^{d-1}.
$$

Including Newton's constant,

$$
a_*\sim \frac{L_*^{d-1}}{G_{d+1}}.
$$

This reproduces the intuition that the number of degrees of freedom decreases along RG flow.

The proof assumes a classical two-derivative gravity description and matter obeying the relevant energy condition. It is not a proof of every field-theoretic $c$-, $a$-, or $F$-theorem in all dimensions. It is a beautiful gravitational reflection of them in a controlled holographic regime.

## First-order flows and fake superpotentials

In many examples, especially supersymmetric ones, the second-order equations can be reduced to first-order flow equations. Introduce a function $W(\phi)$ satisfying

$$
V(\phi)
=
\frac12\left(\frac{dW}{d\phi}\right)^2
-
\frac{d}{4(d-1)}W(\phi)^2.
$$

Then a solution of

$$
\phi'=\frac{dW}{d\phi},
\qquad
A'=-\frac{1}{2(d-1)}W
$$

solves the second-order equations, up to orientation conventions for $u$ and $W$.

When $W$ comes from supersymmetry, these are BPS equations. When no supersymmetry is present, a similar construction may still exist locally and is often called a fake-superpotential formulation.

The important conceptual point is not the terminology. It is that RG flow sometimes becomes a gradient flow in the space of scalar fields.

## Flow to another CFT

Suppose the scalar potential has two AdS critical points:

$$
\partial_\phi V(\phi_{\rm UV})=0,
\qquad
\partial_\phi V(\phi_{\rm IR})=0.
$$

A domain wall interpolating between them represents a flow

$$
\mathrm{CFT}_{\rm UV}
\longrightarrow
\mathrm{CFT}_{\rm IR}.
$$

Near each endpoint, linearized scalar fluctuations determine the spectrum of relevant, marginal, and irrelevant operators at that fixed point. The same bulk scalar may correspond to different operator dimensions in the UV and IR because the AdS radius and the mass matrix at the critical point change.

Such flows are the cleanest nonconformal geometries because both endpoints are under perturbative control. They are also pedagogically useful: every quantity has a conformal interpretation in the UV and in the IR.

## Flow to a gapped endpoint

Many interesting flows do not end at another AdS region. The geometry may cap off smoothly, reach a wall, or develop a singularity. These are candidates for gapped or confining phases.

A smooth cap is usually the most trustworthy. Examples include soliton-like geometries where a spatial circle shrinks smoothly in the interior. The shrinking circle creates an infrared scale and a mass gap.

A singular endpoint requires more care. Some singularities are acceptable as limits of smooth higher-dimensional or stringy solutions. Others signal an inconsistent truncation or an unphysical state. A simple rule of thumb is:

> A singular domain-wall endpoint is not automatically a valid holographic IR.

One should ask whether the singularity can be resolved, whether finite-temperature cloaking is possible, whether probes behave sensibly, and whether the potential satisfies accepted “good singularity” criteria.

## The radial direction as scale: useful but not literal

It is common to say that the radial coordinate is the energy scale. That is useful, but slightly too quick.

A better statement is:

$$
\text{radial slicing of the bulk}
\quad \longleftrightarrow \quad
\text{choice of renormalization scale and scheme}.
$$

Changing the radial cutoff changes the scale at which the boundary effective action is defined. Holographic renormalization makes this precise by treating radial evolution as a Hamilton–Jacobi problem.

However, the radial coordinate is not a gauge-invariant local observable. Different radial gauges can describe the same physics. What is meaningful are quantities such as asymptotic data, renormalized one-point functions, spectra, Wilson loops, thermodynamics, and correlation functions.

## Domain walls versus black branes

A domain wall and a black brane can both be asymptotically AdS, but they describe different physics.

A zero-temperature Poincaré domain wall has metric

$$
ds^2=du^2+e^{2A(u)}\eta_{ij}dx^i dx^j.
$$

It describes a vacuum or ground state of a deformed theory.

A black brane has a horizon and typically takes the form

$$
ds^2
=
\frac{L^2}{z^2}
\left(
- f(z)dt^2+d\mathbf x^2+\frac{dz^2}{f(z)}
\right).
$$

It describes a thermal state. A finite-temperature version of an RG-flow geometry often contains both scalar profiles and a horizon. The scalar encodes deformation or condensate data; the horizon encodes temperature and entropy.

## Relevant, marginal, and irrelevant deformations holographically

For an operator of dimension $\Delta$:

- $\Delta<d$: relevant deformation;
- $\Delta=d$: marginal deformation;
- $\Delta>d$: irrelevant deformation.

The corresponding bulk scalar mass obeys

$$
m^2L^2=\Delta(\Delta-d).
$$

Relevant operators correspond to scalars with

$$
m^2<0
$$

but above the BF bound. The negative mass does not mean instability. It means the dual operator is relevant.

Marginal operators correspond to massless scalars in simple cases:

$$
m^2=0,
\qquad
\Delta=d.
$$

Irrelevant deformations correspond to modes whose sources grow too strongly near the boundary. Turning on irrelevant sources generally spoils the UV AdS boundary condition unless they are treated as part of an effective description with a cutoff. This is one reason bottom-up irrelevant deformations must be handled carefully.

## Example: deformation by a scalar operator

Suppose a $d$-dimensional CFT is deformed by a relevant scalar operator with $\Delta<d$:

$$
S=S_{\rm CFT}+\lambda_{\rm rel}\int d^dx\,\mathcal O.
$$

The dual scalar behaves near the boundary as

$$
\phi(z)
=
\lambda_{\rm rel} z^{d-\Delta}
+
\cdots
+
\phi_{(2\Delta-d)}z^\Delta
+
\cdots.
$$

The first term is the deformation. The second independent datum is the response. For a regular interior solution, $\phi_{(2\Delta-d)}$ is often determined by $\lambda_{\rm rel}$. Dimensional analysis then gives

$$
\langle\mathcal O\rangle
\sim
\lambda_{\rm rel}^{\Delta/(d-\Delta)}
$$

up to dimensionless constants, scheme-dependent contact terms, and possible logarithms.

The scale generated by the deformation is

$$
\Lambda\sim \lambda_{\rm rel}^{1/(d-\Delta)}.
$$

In the bulk, $\Lambda$ is the radial scale at which the scalar backreaction becomes order one.

## What domain walls teach about locality

Domain-wall flows are also a diagnostic for the limitations of effective gravity. If the scalar rolls gently and curvature invariants remain small in string units, a low-energy bulk EFT may be trustworthy. If the flow hits a region of large curvature, a singularity, or a tower of light states, the truncation may fail.

This is why top-down embeddings are valuable. A five-dimensional Einstein-scalar model can be very useful, but without a known string/M-theory origin one must ask whether it satisfies consistency constraints.

In bottom-up applications, the right attitude is not “all models are wrong.” The right attitude is:

> A domain-wall model is a controlled phenomenological laboratory only to the extent that the observables of interest are insensitive to unknown UV or stringy corrections.

## Dictionary checkpoint

| Boundary concept | Bulk domain-wall concept |
|---|---|
| UV CFT | asymptotic AdS region |
| relevant scalar operator $\mathcal O$ | bulk scalar $\phi$ with $m^2L^2=\Delta(\Delta-d)$ |
| source $J$ | non-normalizable coefficient of $\phi$ |
| vev $\langle\mathcal O\rangle$ | normalizable coefficient of $\phi$ after renormalization |
| RG scale $\mu$ | warp factor/radial cutoff, $\mu\sim e^A\sim 1/z$ |
| beta function | radial variation $d\phi/dA$ |
| fixed point | AdS critical point of $V(\phi)$ |
| decrease of degrees of freedom | holographic $c$-function monotonicity |
| mass gap or confinement scale | cap, wall, singular endpoint, or other IR scale |

## Common confusions

### “Any radial dependence is an RG flow.”

Not quite. A black brane has radial dependence, but it describes a thermal state of the same theory, not necessarily a change in the Lagrangian. An RG flow is specifically tied to how the asymptotic data and radial evolution encode scale dependence of the boundary theory or state.

### “A scalar profile always means a source is turned on.”

No. The scalar may be normalizable with no source. Then it represents a vev or a state, not a deformation of the microscopic action.

### “A singular IR is automatically confinement.”

No. A bad singularity may simply mean that the model is inconsistent or that the truncation has failed. Confinement requires physical diagnostics such as a mass gap, discrete spectrum, area-law Wilson loops, or appropriate thermodynamic behavior.

### “The beta function is literally $d\phi/dz$.”

The beta function compares coupling changes to energy-scale changes. Since $\mu\sim e^A\sim 1/z$, the useful quantity is $d\phi/d\log\mu$, often written $d\phi/dA$, not simply $d\phi/dz$.

### “An IR AdS region means no RG flow happened.”

A flow between two CFTs is still a nontrivial RG flow. The theory is scale invariant only at the endpoints. Between them, conformal symmetry is broken by the running coupling.

## Exercises

### Exercise 1: Linearized beta function

Near a UV AdS boundary, suppose a source-driven scalar behaves as

$$
\phi(u)=J e^{-(d-\Delta)u/L}.
$$

Using $A(u)=u/L$, compute

$$
\beta(\phi)=\frac{d\phi}{dA}.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $A=u/L$, we have $dA=du/L$. Therefore

$$
\frac{d\phi}{dA}
=
L\frac{d\phi}{du}
=
L\left[-\frac{d-\Delta}{L}J e^{-(d-\Delta)u/L}\right].
$$

Thus

$$
\beta(\phi)=-(d-\Delta)\phi.
$$

This matches the field-theory expectation that a coupling with engineering dimension $d-\Delta$ grows toward the infrared.

</details>

### Exercise 2: Holographic $c$-function monotonicity

For an Einstein-scalar domain wall,

$$
A''=-\frac{1}{2(d-1)}(\phi')^2.
$$

Show that

$$
a(u)\propto [A'(u)]^{1-d}
$$

is nondecreasing as $u$ increases toward the UV, assuming $A'>0$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{da}{du}
\propto
(1-d)[A']^{-d}A''.
$$

Since $d>1$, $(1-d)<0$. Since

$$
A''=-\frac{1}{2(d-1)}(\phi')^2\le0,
$$

the product is nonnegative:

$$
\frac{da}{du}\ge0.
$$

Thus $a$ increases toward the UV. Equivalently, it decreases along the RG flow from UV to IR.

</details>

### Exercise 3: Central-charge ratio for an AdS-to-AdS flow

A holographic flow connects a UV AdS region of radius $L_{\rm UV}$ to an IR AdS region of radius $L_{\rm IR}$. Assuming the same effective Newton constant, estimate

$$
\frac{c_{\rm IR}}{c_{\rm UV}}.
$$

<details>
<summary><strong>Solution</strong></summary>

For Einstein gravity in $d+1$ dimensions, the effective number of degrees of freedom scales as

$$
c\sim \frac{L^{d-1}}{G_{d+1}}.
$$

If $G_{d+1}$ is unchanged along the flow, then

$$
\frac{c_{\rm IR}}{c_{\rm UV}}
=
\left(\frac{L_{\rm IR}}{L_{\rm UV}}\right)^{d-1}.
$$

A physical RG flow should have fewer degrees of freedom in the IR, so in such examples one expects $L_{\rm IR}<L_{\rm UV}$.

</details>

### Exercise 4: Relevant versus irrelevant sources

Use

$$
\phi(z)=z^{d-\Delta}J+\cdots
$$

to explain why turning on an irrelevant source with $\Delta>d$ is dangerous near the UV boundary.

<details>
<summary><strong>Solution</strong></summary>

If $\Delta>d$, then $d-\Delta<0$, so the source term behaves as

$$
z^{d-\Delta}=z^{-(\Delta-d)}.
$$

As $z\to0$, this diverges. Instead of being a small perturbation of the UV AdS region, the irrelevant source strongly changes the near-boundary geometry. This generally spoils the usual asymptotically AdS boundary condition unless the theory is treated with a UV cutoff or embedded into a more complete UV description.

</details>

## Further reading

- L. Girardello, M. Petrini, M. Porrati, and A. Zaffaroni, [Novel Local CFT and Exact Results on Perturbations of $\mathcal N=4$ Super Yang Mills from AdS Dynamics](https://arxiv.org/abs/hep-th/9810126).
- D. Z. Freedman, S. S. Gubser, K. Pilch, and N. P. Warner, [Renormalization Group Flows from Holography–Supersymmetry and a c-Theorem](https://arxiv.org/abs/hep-th/9904017).
- J. de Boer, E. Verlinde, and H. Verlinde, [On the Holographic Renormalization Group](https://arxiv.org/abs/hep-th/9912012).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- I. Papadimitriou and K. Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
