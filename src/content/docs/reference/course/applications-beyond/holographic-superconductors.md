---
title: "Holographic Superconductors"
description: "How charged black branes become unstable to scalar hair and how the resulting holographic phase models spontaneous U(1) breaking, superfluid response, and superconducting transport."
sidebar:
  label: "Holographic Superconductors"
  order: 90
---

A finite-density holographic system can do something more interesting than remain an ordinary charged black brane. If the bulk contains a charged scalar field, the electric field near a charged horizon can make the scalar effectively unstable. Below a critical temperature, the scalar condenses outside the horizon. The bulk solution becomes a **hairy black brane**, and the boundary theory develops a charged order parameter.

This is the basic mechanism behind holographic superconductors.

The name is historically standard, but there is one important caveat from the start. A bulk gauge field $A_M$ is dual to a **global** conserved current $J^\mu$ in the boundary theory. Therefore the simplest holographic model directly describes a strongly coupled **superfluid** or a phase with spontaneously broken global $U(1)$ symmetry. If one weakly gauges the boundary $U(1)$, the same model can be interpreted as a superconductor. This distinction is not pedantry; it controls what is meant by Meissner physics, boundary photons, and electromagnetic response.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A normal charged black brane becomes unstable below a critical temperature and develops charged scalar hair, which is read as a spontaneous boundary condensate.](/figures/course/holographic-superconductors.svg)

<figcaption>

The minimal holographic superconductor mechanism. A charged black brane with $A_t(z)$ can become unstable because the electric field lowers the effective mass of a charged scalar. The condensed hairy solution has source $\Psi_{(0)}=0$ and response $\langle\mathcal O\rangle\neq0$.

</figcaption>
</figure>

## Why this matters

The simplest finite-density saddle, Reissner–Nordstrom-AdS, is extremely useful but also suspicious. At extremality it has an AdS$_2$ throat and often a nonzero entropy density at $T=0$. One expects many such states to be unstable toward more ordered phases.

Holographic superconductors give the cleanest example. The lesson is broad:

$$
\text{finite density} + \text{charged operator}
\quad\Longrightarrow\quad
\text{possible IR instability}.
$$

The bulk makes this statement geometric. A charged scalar field feels the near-horizon electric field. If the effective mass falls below an appropriate stability bound in the near-horizon region, the normal black brane is no longer the preferred saddle. The new solution carries scalar hair.

The boundary interpretation is just as important. A normal finite-density phase changes into a phase with

$$
\langle \mathcal O \rangle \neq 0,
$$

where $\mathcal O$ is a charged operator. This is spontaneous symmetry breaking: the source for $\mathcal O$ is set to zero, but the expectation value is nonzero.

## The minimal bulk model

A standard bottom-up model is Einstein–Maxwell theory coupled to a charged scalar:

$$
S
=
\frac{1}{16\pi G_{d+1}}
\int d^{d+1}x\sqrt{-g}
\left[
R+\frac{d(d-1)}{L^2}
-\frac{1}{4}F_{MN}F^{MN}
-|D\Psi|^2
-m^2|\Psi|^2
\right]
+
S_{\rm bdy},
$$

with

$$
D_M\Psi=(\nabla_M-iqA_M)\Psi.
$$

The field/operator map is

$$
A_M
\quad\longleftrightarrow\quad
J^\mu,
\qquad
\Psi
\quad\longleftrightarrow\quad
\mathcal O.
$$

The scalar operator $\mathcal O$ is charged under the boundary $U(1)$ current. Condensing $\mathcal O$ therefore spontaneously breaks that $U(1)$.

The equations of motion are

$$
\nabla_M F^{MN}
=
i\left[\Psi^*D^N\Psi-\Psi(D^N\Psi)^*\right],
$$

and

$$
(D_MD^M-m^2)\Psi=0,
$$

together with Einstein's equations if the matter backreacts.

## Probe limit

The first calculation is usually done in the probe limit. One fixes the geometry to be the planar AdS-Schwarzschild black brane and solves only for $A_t$ and $\Psi$. In boundary dimension $d=3$, use

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2+dx^2+dy^2+\frac{dz^2}{f(z)}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^3,
$$

with

$$
T=\frac{3}{4\pi z_h}.
$$

The ansatz is

$$
A=A_t(z)dt,
\qquad
\Psi=\psi(z),
$$

where a gauge choice has made the scalar real.

With $L=1$, the equations become

$$
\psi''+
\left(\frac{f'}{f}-\frac{2}{z}\right)\psi'
+
\left(
\frac{q^2A_t^2}{f^2}
-
\frac{m^2}{z^2f}
\right)\psi=0,
$$

and

$$
A_t''-
\frac{2q^2\psi^2}{z^2f}A_t=0.
$$

These two ordinary differential equations already contain the main physics. The scalar sees the electric potential. The gauge field is depleted by the scalar condensate.

## Boundary conditions

Near the boundary,

$$
A_t(z)=\mu-\rho z+\cdots
\qquad(d=3),
$$

where $\mu$ is the chemical potential and $\rho$ is proportional to the charge density.

The scalar behaves as

$$
\psi(z)
=
z^{3-\Delta}\psi_{(0)}
+
z^\Delta\psi_{(v)}+
\cdots,
\qquad
\Delta(\Delta-3)=m^2L^2.
$$

In standard quantization, $\psi_{(0)}$ is the source and $\psi_{(v)}$ is related to the expectation value. A spontaneous condensate is obtained by imposing

$$
\psi_{(0)}=0,
\qquad
\psi_{(v)}\neq0.
$$

At the horizon, regularity requires

$$
A_t(z_h)=0,
$$

and $\psi(z_h)$ finite. The condition on $A_t$ is easiest to see in Euclidean signature: the thermal circle shrinks at the horizon, so the one-form $A_t d\tau$ must be regular there.

## The normal phase

At high temperature, the scalar vanishes:

$$
\psi(z)=0.
$$

In the probe model, the Maxwell equation gives

$$
A_t(z)=\mu\left(1-\frac{z}{z_h}\right).
$$

This is the normal phase. It describes a finite-density boundary state with no charged condensate.

In a fully backreacted model, the normal phase is a Reissner–Nordstrom-AdS black brane rather than a neutral AdS-Schwarzschild background. The qualitative instability mechanism is the same, but the charged horizon geometry matters quantitatively and can matter qualitatively at low temperature.

## Why the scalar condenses

The charged scalar has an effective mass shifted by the electric potential. Schematically,

$$
m_{\rm eff}^2
=
m^2+q^2g^{tt}A_t^2.
$$

Because $g^{tt}<0$ outside the horizon,

$$
m_{\rm eff}^2
=
m^2-q^2|g^{tt}|A_t^2.
$$

The electric field lowers the effective scalar mass. If the lowering is strong enough in the infrared region, the normal black brane develops a normalizable unstable mode. At the critical temperature $T_c$, the scalar equation has a static solution satisfying

$$
\psi_{(0)}=0,
\qquad
\psi\text{ regular at the horizon}.
$$

Below $T_c$, a nonlinear hairy solution takes over.

In an extremal charged background, the near-horizon region often contains AdS$_2$. Then one can diagnose the instability by checking whether the charged scalar violates the effective AdS$_2$ Breitenlohner–Freedman bound, even if it is perfectly stable with respect to the UV AdS$_{d+1}$ bound.

## Condensate and critical behavior

Near the transition, the condensate usually behaves like

$$
\langle\mathcal O\rangle
\propto
\left(1-\frac{T}{T_c}\right)^{1/2}.
$$

The exponent $1/2$ is mean-field-like. That does not mean the boundary theory is weakly coupled. It means the leading large-$N$ bulk calculation is classical, so fluctuations around the saddle are suppressed.

The critical temperature is not universal. It depends on $m^2$, $q$, the background geometry, the scalar potential, and possible higher-derivative terms. The universal lesson is the saddle structure:

$$
\text{normal charged saddle}
\quad\longrightarrow\quad
\text{hairy charged saddle}.
$$

## Conductivity in the condensed phase

To compute optical conductivity, perturb

$$
\delta A_x(t,z)=a_x(z)e^{-i\omega t}.
$$

In the probe AdS$_4$ model, the perturbation equation is

$$
a_x''+\frac{f'}{f}a_x'
+
\left(
\frac{\omega^2}{f^2}
-
\frac{2q^2\psi^2}{z^2f}
\right)a_x=0.
$$

The condensate gives the gauge-field fluctuation an effective radial mass. The retarded current correlator is obtained by imposing infalling behavior at the horizon and reading the response/source ratio at the boundary:

$$
\sigma(\omega)
=
-\frac{i}{\omega}G^R_{J_xJ_x}(\omega,0).
$$

In the ordered phase, one finds

$$
\operatorname{Im}\sigma(\omega)
\sim
\frac{n_s}{\omega}
\qquad
(\omega\to0),
$$

so the Kramers–Kronig relation implies

$$
\operatorname{Re}\sigma(\omega)
\supset
\pi n_s\delta(\omega).
$$

The coefficient $n_s$ is the superfluid density. Translational invariance can also produce a zero-frequency delta function at finite density, so one must distinguish the momentum-conservation contribution from the superfluid contribution.

## Superfluid or superconductor?

In ordinary AdS/CFT, the boundary value of a bulk gauge field is a source for a global current. It is not automatically a dynamical photon. Therefore the minimal model literally gives a superfluid: a global $U(1)$ is spontaneously broken.

To get an honest superconductor, one must gauge the boundary $U(1)$. In practice, one often imagines coupling the boundary current weakly to an external electromagnetic field. Then the same holographic current response gives superconducting phenomenology.

This distinction is especially important for the Meissner effect. Flux expulsion requires a dynamical boundary gauge field. The bulk scalar hair gives the charged condensate and the superfluid pole; the boundary photon is an extra ingredient.

## Magnetic fields and vortices

A boundary magnetic field corresponds to

$$
F_{xy}^{(0)}=B.
$$

The scalar equation then resembles a charged-particle equation in a magnetic field. Near the upper critical field, the condensate is controlled by lowest-Landau-level physics. With spatial dependence included, vortex-lattice solutions can appear.

This is one of the reasons the model is useful even though it is simple. It captures a geometric mechanism for order, transport, magnetic response, and vortices in one framework.

## Backreaction and low-temperature phases

The probe limit is pedagogically clean but not always physically adequate. With backreaction, the metric must be solved together with $A_t$ and $\psi$. A common ansatz is

$$
ds^2
=
-e^{-\chi(r)}f(r)dt^2
+\frac{dr^2}{f(r)}
+r^2d\vec x^{\,2},
\qquad
A=A_t(r)dt,
\qquad
\Psi=\psi(r).
$$

Backreaction can change the order of the phase transition, the zero-temperature infrared geometry, and the distribution of charge between the horizon and the condensate. The ordered phase may flow to another AdS region, a Lifshitz-like geometry, a hyperscaling-violating geometry, or a more singular endpoint depending on the model.

The safe foundational statement is this: holographic superconductors are not one model, but a family of models in which charged black branes become unstable to charged matter hair.

## What the model teaches and what it does not

The model teaches:

- how spontaneous symmetry breaking appears as black-hole hair;
- how source-free normalizable modes diagnose instabilities;
- how finite-density transport changes in an ordered phase;
- how horizon physics can control strongly coupled many-body behavior;
- how large-$N$ saddle physics produces mean-field-like critical exponents.

The model does not automatically teach:

- the microscopic pairing mechanism of an ordinary material;
- electron-phonon physics;
- lattice momentum relaxation;
- Coulomb screening without gauging the boundary $U(1)$;
- universal critical exponents beyond the classical saddle limit.

The model is best used as a controlled laboratory for strongly coupled order, not as a literal minimal model of every superconductor.

## Dictionary checkpoint

| Boundary concept | Bulk description |
|---|---|
| chemical potential $\mu$ | boundary value of $A_t$ |
| charge density $\rho$ | radial electric flux |
| charged operator $\mathcal O$ | charged scalar $\Psi$ |
| source for $\mathcal O$ | leading scalar coefficient $\Psi_{(0)}$ |
| condensate $\langle\mathcal O\rangle$ | normalizable scalar coefficient |
| normal phase | charged black brane with $\Psi=0$ |
| ordered phase | hairy black brane with $\Psi\neq0$ |
| superfluid density | $1/\omega$ pole in $\operatorname{Im}\sigma$ |
| superconductivity | requires gauging the boundary $U(1)$ |

## Common confusions

### “The bulk scalar is literally a Cooper pair.”

Not necessarily. It is dual to a charged operator. In some phenomenological interpretations that operator plays the role of a pair field, but the minimal model does not contain weakly coupled electrons.

### “The boundary current is automatically electromagnetic.”

No. The current is global unless the boundary symmetry is gauged. The external source $A_\mu^{(0)}$ is not automatically a dynamical photon.

### “The condensate appears because we turned on a source.”

In spontaneous symmetry breaking, the source is set to zero. The condensate is a response selected by horizon regularity and by thermodynamic dominance.

### “The normal phase is always RN-AdS.”

In the probe limit, the background can be neutral AdS-Schwarzschild with a probe Maxwell field. In fully backreacted finite-density models, the normal phase is usually a charged black brane.

### “Infinite DC conductivity proves superconductivity.”

Not by itself. A translationally invariant finite-density system already has infinite DC conductivity from momentum conservation. The superfluid contribution is diagnosed by the additional condensate-related pole structure and, in a gauged system, by Meissner physics.

## Exercises

### Exercise 1: Horizon regularity

Explain why a static electric potential is usually written with $A_t(z_h)=0$ at the horizon.

<details>
<summary><strong>Solution</strong></summary>

In Euclidean signature, the thermal circle shrinks at the horizon. A one-form proportional to the shrinking circle, $A_t d\tau$, is regular at the origin of the polar coordinates only if its coefficient vanishes there, up to a regular gauge transformation. Thus one chooses

$$
A_t(z_h)=0.
$$

The chemical potential is the gauge-invariant potential difference between the boundary and the horizon:

$$
\mu=A_t(0)-A_t(z_h)=A_t(0).
$$

</details>

### Exercise 2: Source-free condensation

For $m^2L^2=-2$ in AdS$_4$, the scalar expansion is

$$
\psi(z)=z\psi_1+z^2\psi_2+\cdots.
$$

In standard quantization with $\Delta=2$, which coefficient should vanish for spontaneous condensation?

<details>
<summary><strong>Solution</strong></summary>

For standard quantization, the source is the coefficient of $z^{3-\Delta}=z$. Therefore the source is $\psi_1$. Spontaneous condensation imposes

$$
\psi_1=0,
$$

while allowing

$$
\psi_2\neq0.
$$

The coefficient $\psi_2$ is proportional, after holographic renormalization and normalization choices, to $\langle\mathcal O_2\rangle$.

</details>

### Exercise 3: Why large charge helps

Using

$$
m_{\rm eff}^2=m^2+q^2g^{tt}A_t^2,
$$

explain why increasing $q$ tends to make the scalar instability easier.

<details>
<summary><strong>Solution</strong></summary>

Outside the horizon, $g^{tt}<0$. Therefore

$$
q^2g^{tt}A_t^2=-q^2|g^{tt}|A_t^2.
$$

Increasing $q$ makes this negative contribution larger. The scalar's effective mass is lowered more strongly by the electric field, so it is more likely to violate an appropriate infrared stability bound and condense.

</details>

### Exercise 4: Superfluid versus superconductor

Why is the minimal holographic superconductor more literally a superfluid?

<details>
<summary><strong>Solution</strong></summary>

The bulk gauge field is dual to a boundary global current. Its boundary value is an external source, not a dynamical photon. A phase with a source-free charged condensate therefore spontaneously breaks a global $U(1)$ symmetry, which is the definition of a superfluid. To obtain a true superconductor, one must additionally gauge the boundary $U(1)$ so that electromagnetic fields become dynamical.

</details>

## Further reading

- S. A. Hartnoll, C. P. Herzog, and G. T. Horowitz, [Building a Holographic Superconductor](https://arxiv.org/abs/0803.3295).
- S. A. Hartnoll, C. P. Herzog, and G. T. Horowitz, [Holographic Superconductors](https://arxiv.org/abs/0810.1563).
- S. A. Hartnoll, [Lectures on holographic methods for condensed matter physics](https://arxiv.org/abs/0903.3246).
- C. P. Herzog, [Lectures on Holographic Superfluidity and Superconductivity](https://arxiv.org/abs/0904.1975).
- G. T. Horowitz, [Introduction to Holographic Superconductors](https://arxiv.org/abs/1002.1722).
