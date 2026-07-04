---
title: "Conformal Collider Bounds"
description: "How positivity of energy measured at null infinity constrains stress-tensor and current three-point data in higher-dimensional conformal field theory."
sidebar:
  label: "Conformal Collider Bounds"
  order: 6
level: Graduate
status: "Polished draft"
source: "Hofman and Maldacena; Rychkov lectures; Simmons-Duffin TASI lectures; conformal collider and ANEC literature."
topics:
  - conformal collider bounds
  - averaged null energy condition
  - stress tensor
  - higher-dimensional CFT
  - causality
canonicalTopics:
  - conformal-collider-bounds
  - averaged-null-energy-condition
  - stress-tensor-three-point-data
researchStatus:
  established:
    - "In unitary Lorentzian CFTs satisfying the appropriate causality and positivity assumptions, energy flux measured at null infinity is nonnegative and constrains stress-tensor and current three-point functions."
  active:
    - "Sharper collider, causality, defect, higher-spin, parity-odd, and holographic constraints remain active research tools, especially in dimensions three and four."
---

## Summary

**Conformal collider bounds** are positivity constraints on CFT data obtained by preparing an excited state and measuring the energy that reaches null infinity. The basic observable is an energy flux operator

$$
\mathcal E(\hat n)
=\lim_{r\to\infty}r^{d-2}\int_{-\infty}^{\infty}du\,T_{uu}(u,r\hat n),
$$

where $\hat n$ is a direction on the celestial sphere and $u=t-r$ is retarded time. In a unitary theory, the measured energy in every direction should be nonnegative:

$$
\langle\Psi|\mathcal E(\hat n)|\Psi\rangle\ge0.
$$

This innocent-looking inequality constrains stress-tensor three-point data, current three-point data, and mixed correlators. In four-dimensional CFTs, the one-point energy flux in a state created by the stress tensor depends on two independent parameters, conventionally called $t_2$ and $t_4$. Positivity imposes a set of linear inequalities on them.

The conceptual point is simple:

$$
\text{positive energy detected far away}
\quad\Longrightarrow\quad
\text{allowed region for CFT three-point data}.
$$

Conformal collider physics is one of the cleanest bridges between Euclidean CFT data, Lorentzian causality, and physical energy measurements.

## Prerequisites

Read [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/), [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/), and [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) first.

You should know that $C_T$ fixes the stress-tensor two-point function, while stress-tensor three-point functions contain additional tensor-structure data in $d>2$.

## Core idea

A collider experiment in an ordinary QFT creates an energetic state, lets it evolve, and measures energy deposited in calorimeters at large distances. A conformal collider is the idealized CFT version of that experiment.

Prepare a state by inserting a local operator near the origin. For example, a stress-tensor state can be created schematically by

$$
|\Psi_\epsilon\rangle=\epsilon^{\mu\nu}T_{\mu\nu}(0)|0\rangle,
$$

with a polarization tensor $\epsilon^{\mu\nu}$. Then measure the energy flux at future null infinity in direction $\hat n$:

$$
\langle\mathcal E(\hat n)\rangle_\epsilon
=\frac{\langle\Psi_\epsilon|\mathcal E(\hat n)|\Psi_\epsilon\rangle}
{\langle\Psi_\epsilon|\Psi_\epsilon\rangle}.
$$

Conformal symmetry fixes the angular dependence of this quantity in terms of the same coefficients that appear in the three-point function

$$
\langle TTT\rangle.
$$

Unitarity says that a calorimeter cannot record negative energy in any direction:

$$
\langle\mathcal E(\hat n)\rangle_\epsilon\ge0
$$

for all allowed polarizations and directions. This produces inequalities on the coefficients in $\langle TTT\rangle$.

The collider bound is therefore a Lorentzian positivity condition on Euclidean-looking CFT data.

## Setup and conventions

The cleanest physical picture is Lorentzian. Use coordinates

$$
x^\pm=t\pm r,
$$

near null infinity, with angular direction $\hat n\in S^{d-2}$. The energy flux operator is

$$
\mathcal E(\hat n)
=\lim_{r\to\infty}r^{d-2}\int_{-\infty}^{\infty}du\,T_{uu}(u,r\hat n).
$$

Equivalently, in light-ray language, the same physics is closely related to the averaged null energy operator

$$
\mathcal E=\int_{-\infty}^{\infty}dx^-\,T_{--}(x^-,x^+=0,\mathbf x_\perp=0).
$$

The averaged null energy condition is

$$
\langle\Psi|\mathcal E|\Psi\rangle\ge0.
$$

Different papers normalize $\mathcal E$, $T_{\mu\nu}$, $C_T$, and stress-tensor three-point coefficients differently. This page emphasizes invariant content. When an explicit four-dimensional formula is displayed, it follows the common Hofman–Maldacena-style $t_2,t_4$ convention.

The assumptions are important: collider bounds are Lorentzian unitarity and positivity statements. They should not be applied blindly to nonunitary CFTs, nonlocal theories, or Euclidean data without reflection positivity.

## Energy flux from a scalar state

As a warmup, create a state with a scalar primary $\mathcal O$:

$$
|\Psi\rangle=\mathcal O|0\rangle.
$$

If $\mathcal O$ has no spin and the state has total energy $E$, rotational symmetry around the state implies an isotropic energy flux:

$$
\langle\mathcal E(\hat n)\rangle=\frac{E}{\operatorname{vol}(S^{d-2})}.
$$

This is automatically nonnegative if $E>0$. No angular collider parameter appears.

Spinning states are more interesting. A spinful operator creates an anisotropic energy distribution. Conformal symmetry fixes the possible angular structures, while positivity restricts their coefficients.

Thus collider bounds begin where spin begins.

## Stress-tensor states in four dimensions

In a four-dimensional CFT, consider a state created by a spatial stress tensor component with symmetric traceless polarization $\epsilon_{ij}$. The normalized energy flux has the form

$$
\langle\mathcal E(\hat n)\rangle_\epsilon
=\frac{E}{4\pi}\left[
1+t_2\left(
\frac{\epsilon^*_{ij}\epsilon_{ik}n^j n^k}{\epsilon^*_{ij}\epsilon_{ij}}-\frac13
\right)
+t_4\left(
\frac{|\epsilon_{ij}n^i n^j|^2}{\epsilon^*_{ij}\epsilon_{ij}}-\frac{2}{15}
\right)
\right].
$$

The constants $t_2$ and $t_4$ are linear combinations of the independent parity-even tensor structures in the stress-tensor three-point function. The subtractions $1/3$ and $2/15$ ensure that the angular average gives the total energy:

$$
\int d\Omega\,\langle\mathcal E(\hat n)\rangle_\epsilon=E.
$$

Positivity for all polarizations gives three inequalities, conventionally associated with tensor, vector, and scalar polarizations relative to the detector direction:

$$
1-\frac13t_2-\frac{2}{15}t_4\ge0,
$$

$$
1+\frac16t_2-\frac{2}{15}t_4\ge0,
$$

and

$$
1+\frac13t_2+\frac{8}{15}t_4\ge0.
$$

These inequalities carve out a triangle in the $(t_2,t_4)$ plane. Free scalar, free fermion, and free vector theories sit at special points on the boundary or corners in common normalizations. Interacting CFTs must lie inside the allowed region, subject to the assumptions of the bound.

## Current collider bounds

One can also create a state with a conserved global symmetry current:

$$
|\Psi_\epsilon^a\rangle=\epsilon^\mu J^a_\mu(0)|0\rangle.
$$

The measured energy flux is controlled by the three-point function

$$
\langle JJT\rangle.
$$

Conformal symmetry and current conservation restrict this correlator to finitely many structures. Positivity of

$$
\langle\mathcal E(\hat n)\rangle_\epsilon
$$

then imposes inequalities on the corresponding coefficients.

Physically, the current collider experiment asks: if a localized charged disturbance is created, how can its energy be distributed at infinity? The answer is not arbitrary. Energy positivity limits the anisotropy of the radiation pattern.

The same idea applies to other spinning operators. The operator used to create the state determines which three-point function controls the angular distribution.

## Relation to the averaged null energy condition

Modern treatments often phrase collider bounds in terms of the averaged null energy condition:

$$
\int_{-\infty}^{\infty}dx^-\,T_{--}(x^-,x^+=0,\mathbf x_\perp)\ge0
$$

as an operator inequality in appropriate states. This condition is called the ANEC.

The ANEC is deeper than a special collider trick. It follows from causality and unitarity assumptions in relativistic QFT and has many consequences:

| Consequence | Meaning |
|---|---|
| Energy-flux positivity | Calorimeters at null infinity record nonnegative energy. |
| Collider bounds | Stress-tensor and current three-point data obey inequalities. |
| Causality constraints | Certain signs in Lorentzian correlators are forbidden. |
| Holographic bounds | Bulk higher-derivative couplings are constrained by boundary positivity. |
| Light-ray operator algebra | Null-integrated operators organize Lorentzian CFT data. |

For a learner, the collider setup is the easiest physical picture. For modern research, the ANEC and light-ray-operator language are often the more flexible framework.

## Holographic interpretation

In holographic CFTs, stress-tensor three-point data map to gravitational interactions in AdS. The Einstein gravity limit gives a special point in collider-parameter space. Higher-derivative terms in the bulk, such as curvature-squared or curvature-cubed interactions, move the CFT away from that point.

Conformal collider bounds then become causality and positivity constraints on bulk gravitational couplings. If a higher-derivative correction allows negative energy flux or superluminal boundary propagation, it is not compatible with a standard unitary causal CFT dual.

This is one reason collider bounds are so useful: they translate a boundary energy measurement into sharp constraints on possible quantum gravities in AdS.

The slogan is

$$
\text{positive energy in the CFT}
\quad\Longleftrightarrow\quad
\text{causal propagation in AdS}.
$$

The equivalence is not literal in every setup, but it is an excellent guide in holographic large-$N$ CFTs.

## Relation to bootstrap

Numerical bootstrap typically begins with Euclidean crossing and reflection positivity. Conformal collider bounds are Lorentzian positivity constraints. They give additional exact information about stress-tensor and current data.

For example, a bootstrap problem involving stress tensors may have parameters describing $\langle TTT\rangle$. Collider positivity restricts those parameters before or alongside solving crossing.

Similarly, if a CFT has a global symmetry current, the current two-point coefficient $C_J$ and the coefficients in $\langle JJT\rangle$ are constrained by Ward identities and collider positivity.

In practice, collider bounds are part of a broader positivity ecosystem:

$$
\text{unitarity bounds},\quad
\lambda^2\ge0,\quad
\text{ANEC},\quad
\text{causality},\quad
\text{crossing}.
$$

Each condition sees a different projection of the same underlying CFT data.

## What the bounds do not determine

Collider bounds are powerful but incomplete. They do not determine the full CFT.

They do not by themselves fix:

| Data | Why not fixed |
|---|---|
| Operator dimensions | Collider bounds constrain certain three-point coefficients, not the whole spectrum. |
| All OPE coefficients | They constrain special correlators involving $T$ or currents. |
| Full stress-tensor three-point function in every dimension | They give inequalities on allowed combinations, not necessarily exact values. |
| Crossing symmetry | A theory must still satisfy OPE associativity. |
| Existence of a CFT | A point satisfying collider bounds may still fail other consistency conditions. |

The correct attitude is that collider bounds are necessary consistency conditions. They are not sufficient conditions for the existence of a CFT.

## Parity-odd structures

In three dimensions, parity-odd tensor structures can appear in current and stress-tensor three-point functions. This is especially important in Chern–Simons–matter theories.

Energy-flux positivity constrains the parity-even and parity-odd data together. The allowed region can be described as a disk- or ball-like region in appropriate variables rather than the four-dimensional triangle above.

The details depend on conventions and on which correlator is considered. The practical lesson is simple:

$$
\text{if parity is not assumed, include parity-odd collider data.}
$$

Ignoring parity-odd structures in a parity-violating theory can lead to artificial or wrong bounds.

## Common pitfalls

**Do not confuse $C_T$ with collider parameters.** $C_T$ normalizes the stress-tensor two-point function. Collider parameters such as $t_2,t_4$ describe stress-tensor three-point shape data.

**Do not apply the bounds without unitarity.** Energy positivity relies on Hilbert-space positivity and Lorentzian causality assumptions. Nonunitary CFTs can evade these bounds.

**Do not forget normalization conventions.** The numerical values of $t_2,t_4$ depend on definitions of tensor structures and stress-tensor normalization. The inequalities above are tied to the displayed four-dimensional flux formula.

**Do not treat the detector direction as an internal index.** The direction $\hat n$ is a point on the celestial sphere. It labels where energy is measured in spacetime.

**Do not assume collider bounds solve crossing.** They are additional necessary constraints, not replacements for the bootstrap equations.

**Do not ignore parity-odd structures.** In three-dimensional parity-violating CFTs, parity-odd stress-tensor and current structures are physical.

**Do not assume the Euclidean and Lorentzian problems are identical.** Collider bounds are Lorentzian statements about null infinity or light-ray operators. Analytic continuation and operator ordering matter.

## Relations to other pages

This page follows [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/), and [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/).

It prepares later pages on [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/), [Holographic CFT](/cft-bootstrap/holographic-cft/), and [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), where ANEC, light-ray operators, causality, and Regge limits become central.

It also connects to [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) because collider experiments are most informative when the state is created by a spinning operator.

## Research status

Conformal collider bounds and ANEC-based positivity constraints are established tools in unitary Lorentzian CFT. Their simplest stress-tensor and current applications are standard.

Active work develops sharper and broader versions: spinning light-ray operators, defects and boundaries, parity-odd structures, supersymmetric collider bounds, holographic causality, higher-spin constraints, and numerical bootstrap systems that incorporate stress-tensor and current positivity data.

## Exercises

### Exercise 1

Show that the four-dimensional stress-tensor energy flux formula averages to the total energy $E$.

<details><summary><strong>Solution</strong></summary>

The formula is

$$
\langle\mathcal E(\hat n)\rangle_\epsilon
=\frac{E}{4\pi}\left[
1+t_2\left(A(\hat n)-\frac13\right)
+t_4\left(B(\hat n)-\frac{2}{15}\right)
\right],
$$

where

$$
A(\hat n)=\frac{\epsilon^*_{ij}\epsilon_{ik}n^j n^k}{\epsilon^*_{ij}\epsilon_{ij}},
\qquad
B(\hat n)=\frac{|\epsilon_{ij}n^i n^j|^2}{\epsilon^*_{ij}\epsilon_{ij}}.
$$

On the unit two-sphere,

$$
\langle n^i n^j\rangle=\frac13\delta^{ij},
$$

so

$$
\langle A\rangle=\frac13.
$$

Similarly,

$$
\langle n^i n^j n^k n^l\rangle
=\frac{1}{15}\left(\delta^{ij}\delta^{kl}+\delta^{ik}\delta^{jl}+\delta^{il}\delta^{jk}\right).
$$

For a traceless symmetric polarization, this gives

$$
\langle B\rangle=\frac{2}{15}.
$$

Therefore the $t_2$ and $t_4$ terms integrate to zero, and

$$
\int d\Omega\,\langle\mathcal E(\hat n)\rangle_\epsilon=E.
$$

</details>

### Exercise 2

Why does a scalar-created state have isotropic energy flux?

<details><summary><strong>Solution</strong></summary>

A scalar primary has no polarization tensor or vector that can choose a preferred direction. If the state has zero spatial momentum and total energy $E$, rotational invariance leaves no angular function on $S^{d-2}$ except a constant. Therefore

$$
\langle\mathcal E(\hat n)\rangle=\frac{E}{\operatorname{vol}(S^{d-2})}.
$$

The integral over directions then gives the total energy $E$.

</details>

### Exercise 3

Explain why collider bounds constrain $\langle TTT\rangle$ rather than just $\langle TT\rangle$.

<details><summary><strong>Solution</strong></summary>

A stress-tensor-created state has the form

$$
|\Psi\rangle\sim T|0\rangle.
$$

The energy flux operator is built from another insertion of $T$. Therefore the expectation value

$$
\langle\Psi|\mathcal E|\Psi\rangle
$$

is determined by a three-point function of stress tensors, schematically

$$
\langle TTT\rangle.
$$

The two-point function $\langle TT\rangle$ fixes the norm of the state and is controlled by $C_T$, but the angular shape of the energy flux depends on stress-tensor three-point tensor structures.

</details>

### Exercise 4

Why are conformal collider bounds necessary but not sufficient consistency conditions?

<details><summary><strong>Solution</strong></summary>

Collider bounds test positivity of certain energy measurements in states created by local operators. Passing these tests means that a subset of Lorentzian positivity constraints is satisfied.

A full CFT must also have a consistent operator spectrum, OPE coefficients, crossing-symmetric four-point functions, appropriate Ward identities, and locality. A choice of three-point coefficients can satisfy collider inequalities but fail crossing or fail to belong to any actual CFT. Therefore collider bounds are necessary, not sufficient.

</details>

## References

- D. M. Hofman and J. Maldacena, “Conformal collider physics: Energy and charge correlations,” *Journal of High Energy Physics* **2008**.
- T. Hartman, S. Kundu, and A. Tajdini, “Averaged null energy condition from causality,” *Journal of High Energy Physics* **2017**.
- D. M. Hofman, D. Li, D. Meltzer, D. Poland, and F. Rejon-Barrera, “A proof of the conformal collider bounds,” *Journal of High Energy Physics* **2016**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-06-30: First polished draft. Added energy flux operators, ANEC connection, four-dimensional $t_2,t_4$ bounds, current collider discussion, holographic interpretation, bootstrap role, pitfalls, exercises, and references.
