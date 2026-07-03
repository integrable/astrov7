---
title: "Conventions and Normalizations"
description: "Core sign, Fourier, state-normalization, propagator, spinor, path-integral, and Euclidean-continuation conventions used throughout qft.org."
sidebar:
  label: "Conventions and Normalizations"
  order: 1
---

## Summary

This page fixes the default conventions used throughout the Foundations of QFT pages. The default metric is mostly-minus,

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

but qft.org supports the mostly-plus convention by giving explicit translation rules. The goal is not to declare one convention morally superior. The goal is to make every sign, factor of $2\pi$, and normalization visible enough that later pages can focus on physics rather than archaeological sign-hunting.

Conventions are not physics, but inconsistent conventions create fake physics. A minus sign in the metric can move into the Klein–Gordon operator, the propagator denominator, the definition of $\gamma^5$, the Wick rotation, or the gauge-field kinetic term. We will choose one default and translate carefully when comparing to sources that use another. For standard examples of these choices, compare Zee's mostly-minus conventions with Weinberg and Srednicki's mostly-plus conventions (Zee 2010, "Convention, Notation, and Units"; Weinberg 1995, Vol. I, Notation; Srednicki 2007, §§1--3).

:::note[Default convention]
Unless a page says otherwise, qft.org uses

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),\qquad c=\hbar=1,
\qquad e^{-ip\cdot x}\text{ for plane waves}.
$$
:::

## Prerequisites

You should be comfortable with special relativity, Fourier transforms, Dirac delta functions, and basic quantum-mechanical bra-ket notation. Spinors, path integrals, and Wick rotation are summarized here only as conventions; their conceptual content is developed later.

## Core idea

A convention page should do three things.

First, it should make the default formulas unambiguous. A reader should know immediately whether $p^2=m^2$ or $p^2=-m^2$, whether the scalar propagator is $i/(p^2-m^2+i\epsilon)$ or $i/(p^2+m^2-i\epsilon)$, and whether the state normalization contains $2E_{\mathbf p}$.

Second, it should make comparison with standard texts painless. Many excellent books use different signatures or Fourier phases. Translating between them is mechanical once the root choices are known.

Third, it should reduce future page bloat. Later pages can say "we use the qft.org conventions" and then get on with the argument. Boring? Yes. Load-bearing? Very.

## Spacetime, indices, and metric

Greek indices run over spacetime components,

$$
\mu,\nu,\rho,\sigma=0,1,2,3,
$$

and Latin indices run over spatial components,

$$
i,j,k=1,2,3.
$$

Repeated upper-lower index pairs are summed. Coordinates are

$$
x^\mu=(t,\mathbf x),\qquad x_\mu=\eta_{\mu\nu}x^\nu=(t,-\mathbf x).
$$

For two four-vectors $a^\mu$ and $b^\mu$,

$$
a\cdot b\equiv \eta_{\mu\nu}a^\mu b^\nu
=a^0b^0-\mathbf a\cdot\mathbf b.
$$

Thus

$$
p^2=(p^0)^2-\mathbf p^2.
$$

For a massive on-shell particle,

$$
p^2=m^2,\qquad p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The derivative conventions are

$$
\partial_\mu=\frac{\partial}{\partial x^\mu}
=(\partial_t,\nabla),
\qquad
\partial^\mu=\eta^{\mu\nu}\partial_\nu=(\partial_t,-\nabla),
$$

so the d'Alembertian is

$$
\Box\equiv \partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

The invariant spacetime volume is written

$$
d^4x=dt\,d^3\mathbf x.
$$

For proper orthochronous Lorentz transformations, $d^4x$ and $d^4p$ are invariant.

### Mostly-plus translation

Some sources use

$$
\eta^{(-)}_{\mu\nu}=\operatorname{diag}(-,+,+,+).
$$

To translate, keep the same components $x^\mu=(t,\mathbf x)$ and replace

$$
\eta^{(-)}_{\mu\nu}=-\eta^{(+)}_{\mu\nu}.
$$

Here $\eta^{(+)}$ means qft.org's mostly-minus metric. Then

| Quantity | qft.org mostly-minus $\eta=(+,-,-,-)$ | mostly-plus $\eta=(-,+,+,+)$ |
|---|---:|---:|
| Four-vector square | $p^2=(p^0)^2-\mathbf p^2$ | $p^2=-(p^0)^2+\mathbf p^2$ |
| Massive mass shell | $p^2=m^2$ | $p^2=-m^2$ |
| d'Alembertian | $\Box=\partial_t^2-\nabla^2$ | $\Box=-\partial_t^2+\nabla^2$ |
| Klein–Gordon equation | $(\Box+m^2)\phi=0$ | $(\Box-m^2)\phi=0$ |
| Scalar propagator denominator | $p^2-m^2+i\epsilon$ | $p^2+m^2-i\epsilon$ |

The entries in the table are equivalent descriptions of the same pole structure. The safest way to translate a formula is to rewrite it in components, replace the metric, and then rebuild covariant notation.

## Units and dimensions

We use natural units,

$$
\hbar=c=1.
$$

Energy, mass, inverse length, and inverse time all have the same dimension. In high-energy units,

$$
[p^\mu]=[m]=[\partial_\mu]=1,
\qquad [x^\mu]=-1.
$$

In four spacetime dimensions, the action is dimensionless and the Lagrangian density has mass dimension four:

$$
S=\int d^4x\,\mathcal L,
\qquad [S]=0,
\qquad [\mathcal L]=4.
$$

For common free fields in $d=4$,

| Object | Mass dimension |
|---|---:|
| scalar field $\phi$ | $1$ |
| Dirac field $\psi$ | $3/2$ |
| gauge field $A_\mu$ | $1$ |
| field strength $F_{\mu\nu}$ | $2$ |
| source $J$ coupled as $J\phi$ | $3$ |

In $d$ spacetime dimensions,

$$
[\phi]=\frac{d-2}{2},\qquad [\psi]=\frac{d-1}{2},\qquad [A_\mu]=\frac{d-2}{2}.
$$

These dimension assignments are bookkeeping devices, but they become central in power counting, renormalization, and effective field theory (Srednicki 2007, §12; Weinberg 1995, Vol. I, ch. 12).

## Fourier transforms

The default spacetime Fourier transform is

$$
f(x)=\int_p e^{-ip\cdot x}\,\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
$$

with

$$
\int_p \equiv \int \frac{d^4p}{(2\pi)^4}.
$$

With the mostly-minus metric,

$$
p\cdot x=p^0t-\mathbf p\cdot\mathbf x,
$$

so

$$
e^{-ip\cdot x}=e^{-ip^0t+i\mathbf p\cdot\mathbf x}.
$$

The corresponding delta-function identity is

$$
\int_p e^{-ip\cdot(x-y)}=\delta^{(4)}(x-y).
$$

For spatial Fourier transforms, we use

$$
f(\mathbf x)=\int_{\mathbf p}e^{i\mathbf p\cdot\mathbf x}\,\widetilde f(\mathbf p),
\qquad
\widetilde f(\mathbf p)=\int d^3\mathbf x\,e^{-i\mathbf p\cdot\mathbf x}f(\mathbf x),
$$

where

$$
\int_{\mathbf p}\equiv \int \frac{d^3\mathbf p}{(2\pi)^3}.
$$

Thus

$$
\int_{\mathbf p}e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}
=\delta^{(3)}(\mathbf x-\mathbf y).
$$

With these phases,

$$
i\partial_\mu e^{-ip\cdot x}=p_\mu e^{-ip\cdot x},
\qquad
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}.
$$

## Delta functions and distributions

The four-dimensional delta function is normalized by

$$
\int d^4x\,\delta^{(4)}(x-y)f(x)=f(y).
$$

The spatial delta function is normalized by

$$
\int d^3\mathbf x\,\delta^{(3)}(\mathbf x-\mathbf y)f(\mathbf x)=f(\mathbf y).
$$

In formulas involving equal-time commutators, $\delta^{(3)}(\mathbf x-\mathbf y)$ is a delta function on a chosen time slice, not a Lorentz-invariant object by itself. The full theory can still be Lorentz invariant; equal-time quantization has simply chosen a frame to describe the canonical algebra.

We write the Heaviside step function as $\theta(t)$, with

$$
\theta(t)=1\quad(t>0),
\qquad
\theta(t)=0\quad(t<0).
$$

Its value at $t=0$ is convention-dependent and does not matter in ordinary distributional manipulations unless contact terms are being tracked explicitly.

## Levi-Civita symbols and dual tensors

We choose

$$
\epsilon^{0123}=+1.
$$

With the mostly-minus metric, lowering all four indices gives

$$
\epsilon_{0123}=-1.
$$

For spatial indices,

$$
\epsilon^{123}=+1.
$$

Dual tensors therefore require metric-signature care. For an antisymmetric tensor $F_{\mu\nu}$, define

$$
\widetilde F^{\mu\nu}
\equiv \frac{1}{2}\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

If you compare to a source with $\epsilon_{0123}=+1$ or a mostly-plus metric, check the signs of all $F\widetilde F$, anomaly, instanton-number, and Hodge-star formulas before importing them.

## Actions and free-field sign conventions

We distinguish the Lagrangian density $\mathcal L$ from the Lagrangian

$$
L=\int d^3\mathbf x\,\mathcal L.
$$

Physicists often say "the Lagrangian" when they mean $\mathcal L$; qft.org will usually spell out "Lagrangian density" when a density is meant.

For a real scalar field,

$$
\mathcal L_0
=\frac{1}{2}\partial_\mu\phi\,\partial^\mu\phi
-\frac{1}{2}m^2\phi^2.
$$

The equation of motion is

$$
(\Box+m^2)\phi=0.
$$

For a complex scalar field,

$$
\mathcal L_0
=\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi.
$$

For a Dirac field,

$$
\mathcal L_0=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

For an Abelian gauge field,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\mathcal L_0=-\frac{1}{4}F_{\mu\nu}F^{\mu\nu}.
$$

With the definitions

$$
E^i=F^{i0},
\qquad
F^{ij}=-\epsilon^{ijk}B^k,
$$

the Maxwell Lagrangian density is

$$
\mathcal L_0=\frac{1}{2}(\mathbf E^2-\mathbf B^2).
$$

## Canonical normalization

For a real scalar field,

$$
\pi(x)=\frac{\partial\mathcal L}{\partial\dot\phi(x)}=\dot\phi(x).
$$

Canonical equal-time quantization uses

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

with

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0,
\qquad
[\pi(t,\mathbf x),\pi(t,\mathbf y)]=0.
$$

For fermions, the canonical brackets are anticommutators. The precise form depends on the chosen fermion variables, but for a Dirac field the standard equal-time relation is

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

The canonical algebra is the starting point for the operator construction of free fields; the path-integral construction reaches the same free propagators after Gaussian integration and the correct $i\epsilon$ prescription (Coleman 2019, chs. 3, 4, 28; Weinberg 1995, Vol. I, chs. 7, 9).

## Relativistic state normalization

The default one-particle normalization is Lorentz covariant:

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

The corresponding one-particle completeness relation is

$$
\mathbf 1_{1\text{-particle}}
=\sum_s\int \frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\mid \mathbf p,s\rangle\langle \mathbf p,s\mid.
$$

The Lorentz-invariant on-shell measure is

$$
d\Pi_p
\equiv \frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=\frac{d^4p}{(2\pi)^3}\,\theta(p^0)\delta(p^2-m^2).
$$

This measure is the default for phase space, LSZ formulas, and free-field mode expansions (Weinberg 1995, Vol. I, §2.5; Srednicki 2007, §§2--3).

Some quantum-mechanics-oriented texts use noncovariant normalization,

$$
\langle \mathbf p'\mid\mathbf p\rangle=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf p').
$$

That convention is fine, but factors of $\sqrt{2E_{\mathbf p}}$ then move into states, fields, and amplitudes. qft.org defaults to the covariant convention because it keeps Lorentz-invariant phase space visible.

## Creation and annihilation operators

For a real scalar field, the default mode expansion is

$$
\phi(x)=\int \frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
\qquad p^0=E_{\mathbf p}.
$$

The operators obey

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\,\delta^{(3)}(\mathbf p-\mathbf q),
$$

with all other scalar creation-annihilation commutators vanishing.

With this convention,

$$
\mid \mathbf p\rangle=a^\dagger(\mathbf p)\mid0\rangle
$$

has precisely the covariant normalization above.

:::tip[Where the $2E_{\mathbf p}$ went]
If a page instead writes

$$
\phi(x)=\int_{\mathbf p}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left[\alpha(\mathbf p)e^{-ip\cdot x}+\alpha^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

then the operators satisfy

$$
[\alpha(\mathbf p),\alpha^\dagger(\mathbf q)]=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf q).
$$

This is the same physics with a different placement of the $2E_{\mathbf p}$ factors.
:::

## Propagators and the iε prescription

For the real scalar field, the default Feynman propagator is

$$
D_F(x-y)
\equiv \langle0\mid T\phi(x)\phi(y)\mid0\rangle
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

It satisfies

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

The $i\epsilon$ term is not decorative. It specifies how the poles are displaced and therefore which Green function is being used. For the Feynman propagator, positive-frequency modes propagate forward in time and negative-frequency modes propagate backward in time; equivalently, the propagator computes a vacuum expectation value of a time-ordered product (Weinberg 1995, Vol. I, §§6.2, 9.2--9.4; Srednicki 2007, §§5, 8--9).

For a Dirac field,

$$
S_F(x-y)
\equiv \langle0\mid T\psi(x)\overline\psi(y)\mid0\rangle
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i(\gamma^\mu p_\mu+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

It satisfies

$$
(i\gamma^\mu\partial_\mu-m)S_F(x-y)=i\delta^{(4)}(x-y).
$$

For a gauge field, the propagator depends on gauge fixing. In Feynman gauge for a massless Abelian gauge field,

$$
D^{\mu\nu}_F(p)=\frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}.
$$

Gauge-dependent propagators are not themselves observables. The gauge-invariant content appears in physical matrix elements and correlation functions of gauge-invariant operators.

## Spinor and gamma-matrix conventions

Gamma matrices satisfy the Clifford algebra

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1.
$$

With the mostly-minus metric,

$$
(\gamma^0)^2=+1,
\qquad
(\gamma^i)^2=-1.
$$

We take

$$
(\gamma^0)^\dagger=\gamma^0,
\qquad
(\gamma^i)^\dagger=-\gamma^i.
$$

The Dirac adjoint is

$$
\overline\psi=\psi^\dagger\gamma^0.
$$

Slash notation means

$$
p\!\!/=\gamma^\mu p_\mu.
$$

The chirality matrix is

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
$$

so

$$
(\gamma^5)^2=1,
\qquad
\{\gamma^5,\gamma^\mu\}=0.
$$

The chiral projectors are

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

The Lorentz-generator matrices acting on Dirac spinors are

$$
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

No particular gamma-matrix representation is assumed unless a page explicitly says so. Representation-independent identities are preferred. When an explicit basis is useful, the page will state whether it is using the Dirac, Weyl, or Majorana basis.

## Gauge-field and charge conventions

For an Abelian gauge field, a field of charge $q$ has covariant derivative

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

The corresponding local gauge transformation is

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

Then

$$
[D_\mu,D_\nu]=iqF_{\mu\nu}.
$$

For the electron, $q=-e$ with $e>0$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

For a non-Abelian gauge theory, unless otherwise stated, generators are Hermitian:

$$
[T^a,T^b]=if^{abc}T^c.
$$

The default matter covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

With this sign choice,

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a,
$$

where

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

Some books use $D_\mu=\partial_\mu-igA_\mu^aT^a$, which flips the sign of the non-Abelian term in $F_{\mu\nu}^a$. The sign of $gA_\mu^aT^a$ is a convention; gauge-invariant predictions do not care as long as the convention is used consistently.

## Path-integral normalization

For a real scalar field in Lorentzian signature, the normalized generating functional is

$$
Z[J]
=\frac{1}{\mathcal N}\int\mathcal D\phi\,
\exp\left\{iS[\phi]+i\int d^4x\,J(x)\phi(x)\right\},
\qquad
Z[0]=1.
$$

Correlation functions are obtained by

$$
\langle0\mid T\phi(x_1)\cdots\phi(x_n)\mid0\rangle
=\left.\frac{1}{i^n}\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

For the free scalar theory,

$$
Z_0[J]
=\exp\left[-\frac{1}{2}\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
$$

where $D_F$ includes the factor of $i$ in momentum space:

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The connected generating functional is defined by

$$
Z[J]=e^{iW[J]},
\qquad
W[J]=-i\log Z[J].
$$

The classical field conjugate to $J$ is

$$
\varphi_J(x)=\frac{\delta W[J]}{\delta J(x)}.
$$

The effective action convention is

$$
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x),
\qquad
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

The normalization $Z[0]=1$ removes disconnected vacuum bubbles from ordinary normalized correlation functions. This is why field-independent factors in Gaussian path integrals usually cancel from normalized observables (Weinberg 1995, Vol. I, §§9.2--9.4; Coleman 2019, chs. 28, 32).

## Euclidean continuation

For mostly-minus Lorentzian signature, the default Wick rotation is

$$
t=-i\tau,
\qquad
p^0=i p_E^0.
$$

Then

$$
p^2=(p^0)^2-\mathbf p^2\mapsto -p_E^2,
\qquad
p_E^2=(p_E^0)^2+\mathbf p^2.
$$

The Lorentzian path-integral weight becomes the Euclidean weight,

$$
e^{iS}\mapsto e^{-S_E}.
$$

For the real scalar field,

$$
S_E[\phi]=\int d\tau\,d^3\mathbf x\,
\left[\frac{1}{2}(\partial_\tau\phi)^2
+\frac{1}{2}(\nabla\phi)^2
+\frac{1}{2}m^2\phi^2\right].
$$

The Euclidean scalar propagator is

$$
G_E(x_E-y_E)
=\int\frac{d^4p_E}{(2\pi)^4}\,
\frac{e^{ip_E\cdot(x_E-y_E)}}{p_E^2+m^2}.
$$

Euclidean QFT is not merely the instruction "replace $t$ by $-i\tau$". Analytic continuation depends on the pole prescription, the spectrum, boundary conditions, and, in a rigorous setting, reflection positivity. Those issues are introduced in the Euclidean QFT and reflection-positivity pages (Schwinger 1958; Osterwalder and Schrader 1973, 1975; Weinberg 1995, Vol. I, ch. 9).

## Common pitfalls

### Confusing metric convention with physics

Changing from $+---$ to $-+++$ should not change a physical prediction. It changes where minus signs live. If a result changes physically after a signature translation, something else changed too.

### Mixing Fourier phases

The pair

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x)
$$

must be kept together. Changing only one phase convention flips signs in momentum-space differential operators and propagators.

### Losing the two-E factor

The invariant measure $d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$ and the covariant state normalization are a matched pair. If you use noncovariant states, the missing $2E_{\mathbf p}$ reappears elsewhere.

### Treating the Feynman propagator as a classical Green function

The Feynman propagator is a time-ordered vacuum two-point function. Retarded and advanced propagators solve causal response problems. These objects are related but not interchangeable.

### Forgetting that path-integral measures can matter

In many elementary Gaussian examples, the measure normalization cancels. In gauge theories, fermion path integrals, anomalies, and curved backgrounds, measure factors and Jacobians can carry physical information.

### Wick rotating tensors casually

Scalar formulas Wick rotate more cleanly than vector, spinor, and gauge-field formulas. Time components, gamma matrices, epsilon tensors, and reality conditions require separate continuation rules.

## Relation to other topics

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) uses these action and Euler--Lagrange conventions.
- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) develops the state normalization and invariant measure.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) derives the scalar mode expansion and canonical commutators.
- [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) applies the scalar action, equation of motion, and propagator conventions.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) explains the $i\epsilon$ prescription in detail.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) discusses Wick rotation and reflection positivity.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) fixes gauge transformations, gauge fixing, and the meaning of gauge symmetry.

## Research status

- **Established:** The formulas on this page are standard textbook conventions. Different sources choose different signs and normalizations, but the translations are mechanical.
- **Active:** None of the convention choices are research questions. However, conventions become delicate in dimensional regularization with chiral fermions, real-time finite-temperature QFT, curved spacetime, anomalies, and Euclidean reconstruction.
- **Speculative:** None.

## Exercises

### Exercise 1: Klein–Gordon signs

Using the mostly-minus metric and

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2,
$$

derive the equation of motion.

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S=\int d^4x\,
\left(\partial_\mu\phi\partial^\mu\delta\phi-m^2\phi\delta\phi\right).
$$

Integrating the first term by parts and dropping the boundary term gives

$$
\delta S=-\int d^4x\,(\partial_\mu\partial^\mu\phi+m^2\phi)\delta\phi.
$$

Since $\delta\phi$ is arbitrary,

$$
(\Box+m^2)\phi=0.
$$

In components this is

$$
(\partial_t^2-\nabla^2+m^2)\phi=0.
$$

</details>

### Exercise 2: Lorentz-invariant measure

Show that

$$
\frac{d^3\mathbf p}{2E_{\mathbf p}}
=d^4p\,\theta(p^0)\delta(p^2-m^2)
$$

up to the shared factor of $(2\pi)^{-3}$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2,
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Using

$$
\delta(f(x))=\sum_i\frac{\delta(x-x_i)}{|f'(x_i)|},
$$

we get

$$
\delta((p^0)^2-E_{\mathbf p}^2)
=\frac{1}{2E_{\mathbf p}}
\left[\delta(p^0-E_{\mathbf p})+\delta(p^0+E_{\mathbf p})\right].
$$

Multiplication by $\theta(p^0)$ keeps only the positive-energy root. Therefore

$$
\int d^4p\,\theta(p^0)\delta(p^2-m^2)F(p)
=\int\frac{d^3\mathbf p}{2E_{\mathbf p}}F(E_{\mathbf p},\mathbf p).
$$

</details>

### Exercise 3: Propagator equation

Verify directly from the Fourier representation that

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

### Exercise 4: Covariant versus noncovariant oscillator normalization

Starting from

$$
\phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

find the rescaled operators $\alpha(\mathbf p)$ for which

$$
[\alpha(\mathbf p),\alpha^\dagger(\mathbf q)]=(2\pi)^3\delta^{(3)}(\mathbf p-\mathbf q).
$$

### Exercise 5: Wick rotation of the scalar denominator

Use $p^0=i p_E^0$ to show that

$$
p^2-m^2+i\epsilon\mapsto -(p_E^2+m^2-i\epsilon).
$$

Explain why the Euclidean propagator has denominator $p_E^2+m^2$.

## References

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, especially §§1--13 for metric conventions, relativistic normalization, scalar quantization, propagators, path integrals, and dimensional analysis.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, Notation and chs. 2, 5--7, 9, 12, for relativistic state normalization, fields, propagators, canonical formalism, path integrals, and power counting.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., "Convention, Notation, and Units" and Part I, for mostly-minus conventions and a compact physics-first introduction.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 1--4, 7--8, 28, for particles, Fock space, scalar fields, Wick expansion, and functional integration.

### For a first pass

- Zee, *Quantum Field Theory in a Nutshell*, Part I.
- Srednicki, *Quantum Field Theory*, §§1--8.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for axiomatic conventions around fields and states.
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973) and **42** (1975), for Euclidean reconstruction and reflection positivity.

## Version history

- **2026-05-22:** Initial qft.org convention lock for the Foundations of QFT section. No figure is included on this page; later pages should add figures only when they clarify a geometric or analytic convention, such as mass shells, light cones, or pole prescriptions.
