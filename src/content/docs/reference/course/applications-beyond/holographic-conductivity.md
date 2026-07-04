---
title: "Holographic Conductivity"
description: "How to compute electrical conductivity in holography from bulk gauge-field perturbations, retarded Green functions, horizon boundary conditions, and membrane paradigm data."
sidebar:
  order: 80
---

## Why this matters

Conductivity is where the finite-density dictionary becomes a laboratory. A boundary electric field is a source for the conserved current $J^i$; the induced current is the response. In holography, this source-response problem becomes a classical boundary-value problem for a bulk gauge-field perturbation.

The basic chain is

$$
\text{boundary electric field}
\quad\longrightarrow\quad
\text{bulk Maxwell perturbation}
\quad\longrightarrow\quad
\text{infalling horizon condition}
\quad\longrightarrow\quad
G^R_{J_xJ_x}
\quad\longrightarrow\quad
\sigma(\omega).
$$

This page explains that chain carefully. It also explains a crucial finite-density subtlety: in a translationally invariant system, the electric current overlaps with conserved momentum, so the DC conductivity is infinite unless momentum can relax or one isolates an incoherent part of the current.

<figure class="doc-figure" style="--figure-width: 58rem;">

![The holographic conductivity computation: a boundary gauge-field source is extended into the bulk, solved with an infalling horizon condition, and converted into a retarded current correlator.](/figures/course/holographic-conductivity.svg)

<figcaption>

The practical holographic conductivity workflow. The boundary value $a_x^{(0)}$ sources $J_x$, the radial canonical momentum $\Pi^x$ gives the response, and infalling regularity at the horizon fixes the retarded correlator. At finite density with exact translations, $J_x$ overlaps with momentum, producing a zero-frequency delta function.

</figcaption>
</figure>

## Linear response and the Kubo formula

Turn on a weak boundary gauge-field source

$$
\delta A_x^{(0)}(t)=a_x^{(0)}(\omega)e^{-i\omega t}.
$$

In gauge $A_t^{(0)}=0$, the boundary electric field is

$$
E_x(\omega)=i\omega a_x^{(0)}(\omega).
$$

Linear response says

$$
\langle J_x(\omega)\rangle
=
G^R_{J_xJ_x}(\omega,\vec k=0)\,a_x^{(0)}(\omega).
$$

Ohm's law is

$$
\langle J_x(\omega)\rangle
=
\sigma(\omega)E_x(\omega).
$$

Therefore

$$
\sigma(\omega)
=
\frac{1}{i\omega}G^R_{J_xJ_x}(\omega,0)
=
-\frac{i}{\omega}G^R_{J_xJ_x}(\omega,0).
$$

The sign convention depends on Fourier convention. In this course we use $e^{-i\omega t}$, so the formula above is the standard one.

## Bulk setup

Take a bulk Maxwell sector

$$
S_A
=
-\frac{1}{4g_F^2}
\int d^{d+1}x\sqrt{-g}\,Z(\phi)F_{MN}F^{MN}.
$$

The function $Z(\phi)$ is a gauge kinetic coupling. In simple Einstein–Maxwell theory, $Z=1$. In bottom-up models or consistent truncations, $Z$ can depend on neutral scalar fields and strongly affect transport.

To compute the longitudinally homogeneous optical conductivity, perturb

$$
\delta A_x(t,r)=a_x(r)e^{-i\omega t},
\qquad
\vec k=0.
$$

For a neutral background, or in a probe limit where metric fluctuations can be ignored, the Maxwell equation becomes

$$
\partial_r
\left(
\frac{\sqrt{-g}}{g_F^2}Z g^{rr}g^{xx}\partial_r a_x
\right)
+
\frac{\sqrt{-g}}{g_F^2}Z g^{tt}g^{xx}\omega^2 a_x=0.
$$

The radial canonical momentum conjugate to $a_x$ is

$$
\Pi^x(r)
=
-\frac{1}{g_F^2}\sqrt{-g}\,Z g^{rr}g^{xx}\partial_r a_x.
$$

The retarded Green function is obtained by evaluating the renormalized response-to-source ratio at the boundary:

$$
G^R_{J_xJ_x}(\omega,0)
=
\lim_{r\to\infty}\frac{\Pi^x_{\mathrm{ren}}(r)}{a_x(r)}.
$$

In Fefferman–Graham or $z$ coordinates, replace $r\to\infty$ by $z\to0$. The formula is the same idea: canonical momentum divided by boundary value.

## Infalling boundary condition

The retarded correlator is selected by an infalling condition at the future horizon. Near a nonextremal horizon, introduce the tortoise coordinate $r_*$ such that outgoing and infalling waves behave as

$$
e^{-i\omega(t-r_*)},
\qquad
 e^{-i\omega(t+r_*)}.
$$

The retarded prescription chooses the infalling wave:

$$
a_x(r)
\sim
(r-r_h)^{-i\omega/(4\pi T)}
$$

in a radial coordinate where the horizon is at $r=r_h$.

This condition is not a decorative detail. Without it, the same differential equation would compute a different Green function.

## Horizon formula in the low-frequency limit

For a diagonal metric

$$
ds^2
=
-g_{tt}(r)dt^2+g_{rr}(r)dr^2+g_{xx}(r)d\vec x^{\,2},
$$

with $g_{tt},g_{rr},g_{xx}>0$ as functions in this notation, the infalling condition gives near the horizon

$$
\partial_r a_x
\simeq
-i\omega\sqrt{\frac{g_{rr}}{g_{tt}}}\,a_x .
$$

Plugging this into the canonical momentum yields the low-frequency membrane expression

$$
\sigma_{\mathrm{DC}}^{\mathrm{probe}}
=
\left.
\frac{1}{g_F^2}
\sqrt{-g}\,Z g^{xx}\sqrt{-g^{tt}g^{rr}}
\right|_{r=r_h} .
$$

This formula applies to the decoupled Maxwell fluctuation. It is often called a membrane-paradigm result: the low-frequency response can be read from horizon data.

For example, in a neutral AdS$_4$ black brane with $Z=1$, the answer is simply

$$
\sigma=\frac{1}{g_F^2}
$$

in appropriate units. In fact, electromagnetic self-duality in four bulk dimensions makes the optical conductivity frequency independent in the simplest Maxwell theory.

## Radial flow of conductivity

It is useful to define a radial conductivity

$$
\sigma(r,\omega)
=
\frac{\Pi^x(r)}{i\omega a_x(r)}.
$$

The Maxwell equation becomes a first-order radial flow equation for $\sigma(r,\omega)$. The horizon condition sets the initial value, and the boundary value gives the field-theory conductivity:

$$
\sigma(\omega)
=
\lim_{r\to\infty}\sigma(r,\omega).
$$

In the strict $\omega\to0$ limit and for a decoupled Maxwell mode, the radial flow often becomes trivial, so the horizon value equals the boundary value. At finite frequency, the flow is nontrivial: the conductivity is not determined by the horizon alone.

## The finite-density momentum problem

At finite charge density, the current $J_x$ usually overlaps with momentum $P_x$. In a translationally invariant system, momentum is conserved. A uniform electric field accelerates the charged fluid forever. Therefore the DC conductivity contains a delta function:

$$
\operatorname{Re}\sigma(\omega)
\supset
\pi\frac{\rho^2}{\epsilon+P}\delta(\omega),
$$

and by Kramers–Kronig,

$$
\operatorname{Im}\sigma(\omega)
\supset
\frac{\rho^2}{\epsilon+P}\frac{1}{\omega}.
$$

Here $\rho$ is charge density, $\epsilon$ is energy density, and $P$ is pressure.

This is not an exotic holographic effect. It is ordinary hydrodynamics. If translations are exact and the current carries momentum, the DC conductivity is infinite.

In the bulk, this appears because the gauge perturbation $a_x$ couples to a metric perturbation $h_{tx}$ in charged backgrounds. The coupled system computes the full electric response, including momentum drag.

There are three common ways to get a finite DC conductivity:

1. work at zero density, where $J_x$ need not overlap with momentum;
2. study a probe sector whose charge does not significantly backreact on the momentum-carrying background;
3. break translations explicitly or spontaneously, for example with lattices, axions, disorder, massive gravity, Q-lattices, or brane defects.

The clean translationally invariant finite-density answer is not “a finite number.” It is a distribution with a zero-frequency delta function plus a regular part.

## Incoherent conductivity

Even in a translationally invariant finite-density system, one can define a current orthogonal to momentum:

$$
J_{\mathrm{inc}}^i
=
J^i-\frac{\rho}{\epsilon+P}T^{ti}.
$$

This current does not drag the conserved momentum. Its conductivity is finite and physically meaningful. In holography, the corresponding bulk fluctuation is a gauge-invariant combination of $a_i$ and metric perturbations.

The precise formula depends on the model, but the conceptual point is important:

$$
\text{full electric conductivity}
=
\text{momentum pole}+
\text{incoherent response}.
$$

The membrane paradigm often computes the latter cleanly in the low-frequency limit.

## A concrete neutral example: Maxwell in AdS$_4$ Schwarzschild

Consider

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2+dx^2+dy^2+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^3 .
$$

For a Maxwell perturbation $a_x(z)e^{-i\omega t}$, the equation is

$$
\partial_z\left(f\partial_z a_x\right)
+
\frac{\omega^2}{f}a_x=0.
$$

The canonical momentum is

$$
\Pi^x
=
-\frac{1}{g_F^2}f\partial_z a_x.
$$

At the horizon, infalling behavior gives

$$
\partial_z a_x
\simeq
\frac{i\omega}{f}a_x,
$$

up to a sign depending on whether the radial coordinate increases toward or away from the horizon. The conductivity is

$$
\sigma(\omega)
=
\frac{\Pi^x}{i\omega a_x}
=
\frac{1}{g_F^2}.
$$

The fact that this simple answer holds for all $\omega$ in this model is special to four bulk dimensions with constant Maxwell coupling. It is not true in generic backgrounds.

## Conductivity and the AdS$_2$ throat

In charged near-extremal backgrounds, the low-frequency optical conductivity is often controlled by the AdS$_2$ throat discussed on the previous page. The logic is the same as for scalar and fermion correlators:

1. identify the IR mode in the AdS$_2$ region;
2. compute its IR Green function $\mathcal G_{\mathrm{IR}}(\omega)$;
3. match it to the UV region;
4. extract the boundary current correlator.

Schematically,

$$
G^R_{J_xJ_x}(\omega)
=
G_0+G_1\mathcal G_{\mathrm{IR}}(\omega)+\cdots .
$$

The exponent of the nonanalytic frequency dependence is determined by the AdS$_2$ dimension of the IR operator that couples to the current. In many simple Einstein–Maxwell systems, the current mixes with metric perturbations, so the actual IR eigenmodes are not just the bare Maxwell fluctuation $a_x$.

This is why one should be cautious about saying “the conductivity scales like $\omega^{2\nu-1}$” without specifying the model and the gauge-invariant perturbation.

## Practical computation recipe

For a standard optical-conductivity calculation:

1. **Choose the background.** Decide whether it is neutral, charged, probe, backreacted, translationally invariant, or momentum relaxing.
2. **Choose perturbations.** At $k=0$, start with $a_x(r)e^{-i\omega t}$. In a charged backreacted background, include the coupled metric perturbation $h_{tx}$ and possibly scalar perturbations.
3. **Build gauge-invariant variables.** Remove residual diffeomorphism and gauge redundancy.
4. **Impose infalling conditions.** Near the future horizon, choose the infalling solution.
5. **Integrate to the boundary.** Solve the linear ODE system analytically in limits or numerically in general.
6. **Read source and response.** Expand near the boundary and compute renormalized canonical momenta.
7. **Apply the Kubo formula.** Use $\sigma(\omega)=-iG_R(\omega,0)/\omega$.
8. **Check Ward identities.** Especially at finite density, verify momentum-related poles and contact terms.

This is the same GKPW logic as before, now in the real-time linear-response setting.

## Dictionary checkpoint

The core conductivity dictionary is

| Boundary transport object | Bulk object |
|---|---|
| electric field $E_x$ | time-dependent boundary value $a_x^{(0)}$ |
| current response $\langle J_x\rangle$ | radial canonical momentum $\Pi^x$ |
| retarded correlator $G^R_{J_xJ_x}$ | infalling bulk solution response/source ratio |
| optical conductivity $\sigma(\omega)$ | $-iG_R/\omega$ |
| DC membrane conductivity | horizon data in the low-frequency limit |
| infinite clean finite-density DC conductivity | momentum conservation and gauge-metric mixing |

A useful formula to remember is

$$
\sigma(\omega)
=
\lim_{r\to\infty}
\frac{\Pi^x(r)}{i\omega a_x(r)}.
$$

A useful warning to remember is

$$
\rho\neq0\quad\text{and exact translations}
\quad\Rightarrow\quad
\operatorname{Re}\sigma(\omega)\text{ contains a }\delta(\omega)\text{ term}.
$$

## Common confusions

### “The horizon formula always gives the full conductivity.”

No. Horizon data determine certain low-frequency transport coefficients, especially for decoupled modes or carefully chosen incoherent currents. At finite frequency, the radial evolution from the horizon to the boundary matters.

### “Finite charge density automatically means finite DC conductivity.”

Usually the opposite. If translations are exact and $\rho\neq0$, the electric field accelerates momentum forever, producing an infinite DC conductivity.

### “The bulk Maxwell field is the physical photon.”

No. In standard AdS/CFT, the boundary $U(1)$ is a global symmetry. The bulk gauge field is dual to the global current. One can weakly gauge the boundary symmetry as an extra operation, but that is not automatic.

### “The conductivity is always universal.”

No. Some quantities are universal in special two-derivative settings or due to electromagnetic self-duality. Generic frequency-dependent conductivity depends on the full radial geometry and bulk couplings.

### “One can ignore metric perturbations at finite density.”

Not in a backreacted charged background with exact translations. The Maxwell perturbation generally couples to metric perturbations because electric current carries momentum.

## Exercises

### Exercise 1: Derive the Kubo formula

Assume

$$
\langle J_x\rangle=G^R_{J_xJ_x}a_x^{(0)},
\qquad
E_x=i\omega a_x^{(0)}.
$$

Derive the expression for $\sigma(\omega)$.

<details>
<summary><strong>Solution</strong></summary>

Ohm's law gives

$$
\langle J_x\rangle=\sigma E_x.
$$

Using $E_x=i\omega a_x^{(0)}$,

$$
G^R_{J_xJ_x}a_x^{(0)}
=
\sigma i\omega a_x^{(0)}.
$$

Therefore

$$
\sigma(\omega)
=
\frac{G^R_{J_xJ_x}(\omega,0)}{i\omega}
=
-\frac{i}{\omega}G^R_{J_xJ_x}(\omega,0).
$$

</details>

### Exercise 2: Horizon membrane conductivity

For a decoupled Maxwell fluctuation in a diagonal metric, use the infalling relation

$$
\partial_r a_x
\simeq
-i\omega\sqrt{\frac{g_{rr}}{g_{tt}}}a_x
$$

and

$$
\Pi^x
=
-\frac{1}{g_F^2}\sqrt{-g}\,Zg^{rr}g^{xx}\partial_r a_x
$$

to derive the horizon formula for $\sigma_{\mathrm{DC}}$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the infalling derivative into the canonical momentum:

$$
\Pi^x
=
\frac{i\omega}{g_F^2}
\sqrt{-g}\,Zg^{rr}g^{xx}
\sqrt{\frac{g_{rr}}{g_{tt}}}a_x .
$$

Using $g^{rr}=1/g_{rr}$ and $-g^{tt}=1/g_{tt}$,

$$
g^{rr}\sqrt{\frac{g_{rr}}{g_{tt}}}
=
\sqrt{-g^{tt}g^{rr}}.
$$

Thus

$$
\frac{\Pi^x}{i\omega a_x}
=
\frac{1}{g_F^2}
\sqrt{-g}\,Zg^{xx}\sqrt{-g^{tt}g^{rr}} .
$$

Evaluating at the horizon gives

$$
\sigma_{\mathrm{DC}}^{\mathrm{probe}}
=
\left.
\frac{1}{g_F^2}
\sqrt{-g}\,Zg^{xx}\sqrt{-g^{tt}g^{rr}}
\right|_{r_h}.
$$

</details>

### Exercise 3: Why is the clean finite-density DC conductivity infinite?

Use the fact that momentum is conserved and that a finite charge density gives a nonzero overlap between electric current and momentum.

<details>
<summary><strong>Solution</strong></summary>

At finite density, part of the electric current is simply the motion of the charged fluid. In relativistic hydrodynamics,

$$
J^x\supset \rho v^x,
\qquad
T^{tx}=(\epsilon+P)v^x.
$$

Thus

$$
J^x\supset \frac{\rho}{\epsilon+P}T^{tx}.
$$

If translations are exact, $T^{tx}$ is conserved at zero spatial momentum. A uniform electric field accelerates this conserved momentum and produces a response that does not decay. In frequency space this gives

$$
\operatorname{Im}\sigma(\omega)
\sim
\frac{\rho^2}{\epsilon+P}\frac{1}{\omega},
$$

and therefore a delta function in $\operatorname{Re}\sigma$.

</details>

### Exercise 4: Conductivity in neutral AdS$_4$ Maxwell theory

For the neutral AdS$_4$ black brane, the Maxwell equation is

$$
\partial_z(f\partial_z a_x)+\frac{\omega^2}{f}a_x=0.
$$

Show that the near-horizon infalling condition implies $\sigma=1/g_F^2$ at low frequency.

<details>
<summary><strong>Solution</strong></summary>

Near the horizon, infalling behavior gives

$$
\partial_z a_x\simeq \frac{i\omega}{f}a_x
$$

up to the sign convention for $z$. The canonical momentum is

$$
\Pi^x=-\frac{1}{g_F^2}f\partial_z a_x.
$$

Therefore

$$
\Pi^x\simeq -\frac{i\omega}{g_F^2}a_x.
$$

Depending on the radial orientation convention, the Kubo sign compensates this sign. The magnitude of the conductivity is

$$
\sigma=\frac{1}{g_F^2}.
$$

In this special four-dimensional bulk Maxwell theory, electromagnetic self-duality extends this low-frequency result to all frequencies.

</details>

## Further reading

- D. T. Son and A. O. Starinets, [Minkowski-space correlators in AdS/CFT correspondence](https://arxiv.org/abs/hep-th/0205051).
- P. Kovtun, D. T. Son, and A. O. Starinets, [Holography and hydrodynamics: diffusion on stretched horizons](https://arxiv.org/abs/hep-th/0309213).
- N. Iqbal and H. Liu, [Universality of the hydrodynamic limit in AdS/CFT and the membrane paradigm](https://arxiv.org/abs/0809.3808).
- S. A. Hartnoll, [Lectures on holographic methods for condensed matter physics](https://arxiv.org/abs/0903.3246).
- C. P. Herzog, [Lectures on Holographic Superfluidity and Superconductivity](https://arxiv.org/abs/0904.1975).
- S. A. Hartnoll and C. P. Herzog, [Ohm's Law at strong coupling: S duality and the cyclotron resonance](https://arxiv.org/abs/0706.3228).
