---
title: "Conventions and Notation"
description: "Metric, curvature, stress-tensor, boundary, Euclidean, black-hole, and holographic conventions for the Spacetime, Gravity, and Holography volume."
sidebar:
  label: "Conventions and Notation"
  order: 10
level: Graduate
status: "Polished draft"
source: "Wald 1984; Carroll 2004; Birrell and Davies 1982; Parker and Toms 2009; Wald 1994; Poisson 2004; Hawking and Ellis 1973; Nakahara 2018, chs. 5, 7, and 9–11; Frankel 2011, chs. 2–3 and 9–11; Zee 2010, chs. I.11 and VIII.1–VIII.3; Weinberg 1995, Vol. I, Notation; Skenderis 2002; de Haro, Skenderis, and Solodukhin 2001"
topics:
  - curved-spacetime conventions
  - curvature signs
  - stress tensor
  - gravitational action
  - holographic conventions
canonicalTopics:
  - curved-spacetime-conventions
  - riemann-curvature-convention
  - einstein-hilbert-action
  - stress-tensor-normalization
  - holographic-renormalization-conventions
researchStatus:
  established:
    - "The sign, normalization, and variational conventions on this page fix the default language for curved-spacetime QFT, semiclassical gravity, black-hole thermodynamics, and holography in this volume."
  active:
    - "Different subfields use incompatible curvature, metric-signature, Euclidean-action, and Brown–York stress-tensor conventions; comparison with outside sources should always begin by translating conventions."
---

## Summary

This page fixes the conventions used in this volume. The defaults extend the site-wide mostly-minus convention to curved spacetime, gravity, black holes, and holography. Unless a page says otherwise, we use natural units and Lorentzian signature

$$
\hbar=c=k_B=1,
\qquad
\eta_{ab}=\operatorname{diag}(+,-,\ldots,-).
$$

The Riemann tensor is defined by

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=
R^\rho{}_{\sigma\mu\nu}V^\sigma,
\qquad
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu}.
$$

With this convention, a round Riemannian sphere has positive scalar curvature, de Sitter has positive scalar curvature, and anti-de Sitter has negative scalar curvature. In $D$ spacetime dimensions,

$$
\text{AdS}_D(L):
\qquad
R_{\mu\nu}=-\frac{D-1}{L^2}g_{\mu\nu},
\qquad
R=-\frac{D(D-1)}{L^2}.
$$

The gravitational action is normalized as

$$
S_{\mathrm{grav}}
=
\frac{1}{2\kappa_D^2}
\int_M d^Dx\,\sqrt{|g|}\,(R-2\Lambda),
\qquad
\kappa_D^2=8\pi G_D,
$$

up to boundary and counterterm contributions. The matter stress tensor is

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}\frac{\delta S_{\mathrm m}}{\delta g^{\mu\nu}},
\qquad
\delta S_{\mathrm m}
=-\frac12\int_M d^Dx\,\sqrt{|g|}\,
T_{\mu\nu}\,\delta g^{\mu\nu}.
$$

These choices imply the Einstein equation

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}
=
\kappa_D^2T_{\mu\nu},
\qquad
G_{\mu\nu}=R_{\mu\nu}-\frac12Rg_{\mu\nu}.
$$

Conventions are not a philosophical garnish. They decide the sign of the Klein–Gordon operator in curved spacetime, the sign of the cosmological constant for AdS, the sign of the trace anomaly, the normalization of black-hole entropy, and the factor of two in every holographic stress tensor. This page is the antidote to sign archaeology.

:::note[Default convention]
Unless explicitly stated otherwise, this volume uses mostly-minus Lorentzian signature, $e^{-ip\cdot x}$ plane waves inherited from the site-wide conventions, the Riemann convention above, and $\kappa_D^2=8\pi G_D$.
:::

## Prerequisites

You should know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/), especially the mostly-minus metric, Fourier phase, state normalization, and Wick-rotation conventions. You should also be comfortable with tensor notation, differential forms at a basic level, and the idea that a QFT can be coupled to nondynamical background sources.

The first geometry page in this volume, [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/), develops the geometric language used below.

## Core idea

Flat-space QFT has a small number of sign choices. Curved-spacetime QFT and holography have many more. A result can change appearance when one changes any of the following:

| Choice | What it affects |
|---|---|
| Metric signature | Mass shells, wave operators, gamma matrices, signs in kinetic terms. |
| Riemann tensor sign | Signs of $R_{\mu\nu}$, $R$, Einstein equations, and curvature couplings. |
| Stress-tensor definition | Ward identities, trace anomalies, Brown–York tensors, response functions. |
| Boundary normal | Gibbons–Hawking–York term, extrinsic curvature, quasilocal energy. |
| Euclidean continuation | Thermal circles, saddle weights, black-hole actions, entropy. |
| AdS radial convention | Source/vev identification, counterterms, holographic stress tensor. |

The rule is simple: formulas in this volume are internally consistent, but outside references must be translated before comparing signs.

## Dimensions, indices, and metrics

We use $D$ for the spacetime dimension of a curved spacetime or bulk gravitational theory. In holography, the boundary QFT dimension is usually $d=D-1$.

Curved spacetime indices are Greek,

$$
\mu,\nu,\rho,\sigma=0,1,\ldots,D-1,
$$

while local Lorentz-frame indices are Latin from the beginning of the alphabet,

$$
a,b,c,d=0,1,\ldots,D-1.
$$

Spatial indices on a chosen time slice are Latin from the middle of the alphabet,

$$
i,j,k=1,\ldots,D-1.
$$

The metric has one positive timelike direction and $D-1$ negative spacelike directions. In a local orthonormal frame,

$$
\eta_{ab}=\operatorname{diag}(+,-,\ldots,-).
$$

The line element is

$$
ds^2=g_{\mu\nu}(x)dx^\mu dx^\nu.
$$

With our signature,

| Vector $v^\mu$ | Condition | Interpretation |
|---|---:|---|
| Timelike | $g_{\mu\nu}v^\mu v^\nu>0$ | Possible tangent to a massive worldline. |
| Null | $g_{\mu\nu}v^\mu v^\nu=0$ | Possible tangent to a light ray. |
| Spacelike | $g_{\mu\nu}v^\mu v^\nu<0$ | Outside the local light cone. |

For a timelike curve $x^\mu(\lambda)$, proper time satisfies

$$
d\tau^2=ds^2>0.
$$

For a spacelike curve, proper length is $d\ell^2=-ds^2>0$.

The invariant volume element is

$$
d\mathrm{vol}_g=d^Dx\,\sqrt{|g|},
\qquad
|g|=|\det g_{\mu\nu}|.
$$

In four Lorentzian dimensions with mostly-minus signature, $\det g_{\mu\nu}<0$, so $\sqrt{|g|}=\sqrt{-g}$. In arbitrary dimension, $\sqrt{|g|}$ avoids a pointless even/odd sign trap.

## Covariant derivatives and curvature

The Levi-Civita connection is torsion-free and metric-compatible:

$$
\Gamma^\rho{}_{\mu\nu}=\Gamma^\rho{}_{\nu\mu},
\qquad
\nabla_\rho g_{\mu\nu}=0.
$$

In coordinates,

$$
\Gamma^\rho{}_{\mu\nu}
=
\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\nu\sigma}
+\partial_\nu g_{\mu\sigma}
-\partial_\sigma g_{\mu\nu}
\right).
$$

For a vector and a covector,

$$
\nabla_\mu V^\nu=\partial_\mu V^\nu
+\Gamma^\nu{}_{\mu\rho}V^\rho,
\qquad
\nabla_\mu \omega_\nu=\partial_\mu\omega_\nu
-\Gamma^\rho{}_{\mu\nu}\omega_\rho.
$$

The curvature convention is

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=
R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

Equivalently,

$$
R^\rho{}_{\sigma\mu\nu}
=
\partial_\mu\Gamma^\rho{}_{\nu\sigma}
-\partial_\nu\Gamma^\rho{}_{\mu\sigma}
+\Gamma^\rho{}_{\mu\lambda}\Gamma^\lambda{}_{\nu\sigma}
-\Gamma^\rho{}_{\nu\lambda}\Gamma^\lambda{}_{\mu\sigma}.
$$

The Ricci tensor and scalar curvature are

$$
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu}.
$$

The Einstein tensor is

$$
G_{\mu\nu}=R_{\mu\nu}-\frac12Rg_{\mu\nu},
\qquad
\nabla^\mu G_{\mu\nu}=0.
$$

Useful curvature tests are:

$$
\begin{array}{rcl}
\text{round }S^D(L):
& R_{ij}=\dfrac{D-1}{L^2}g_{ij},
& R=\dfrac{D(D-1)}{L^2},\\
\text{dS}_D(L):
& R_{\mu\nu}=\dfrac{D-1}{L^2}g_{\mu\nu},
& R=\dfrac{D(D-1)}{L^2},\\
\text{AdS}_D(L):
& R_{\mu\nu}=-\dfrac{D-1}{L^2}g_{\mu\nu},
& R=-\dfrac{D(D-1)}{L^2}.
\end{array}
$$

If a text gives the opposite Riemann convention, its $R^\rho{}_{\sigma\mu\nu}$, $R_{\mu\nu}$, $R$, and Einstein–Hilbert Lagrangian sign must be translated together.

## Fields on curved spacetime

The minimal replacement rule is

$$
\eta_{\mu\nu}\to g_{\mu\nu},
\qquad
\partial_\mu\to\nabla_\mu,
\qquad
d^Dx\to d^Dx\sqrt{|g|}.
$$

That slogan is useful but incomplete. Curvature permits new local couplings. For example, a real scalar field may have the action

$$
S_\phi
=
\frac12\int d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\nabla_\mu\phi\nabla_\nu\phi
-(m^2+\xi R)\phi^2
\right),
$$

with equation of motion

$$
(\Box_g+m^2+\xi R)\phi=0,
\qquad
\Box_g\phi
=\nabla_\mu\nabla^\mu\phi.
$$

For scalars,

$$
\Box_g\phi
=
\frac{1}{\sqrt{|g|}}\partial_\mu
\left(\sqrt{|g|}\,g^{\mu\nu}\partial_\nu\phi\right).
$$

The conformal scalar coupling in $D$ spacetime dimensions is

$$
\xi_c=\frac{D-2}{4(D-1)}.
$$

Spinor fields require a vielbein $e^a{}_\mu$:

$$
g_{\mu\nu}=e^a{}_\mu e^b{}_\nu\eta_{ab},
\qquad
\gamma^\mu=e^\mu{}_a\gamma^a,
\qquad
\{\gamma^\mu,\gamma^\nu\}=2g^{\mu\nu}.
$$

Their covariant derivative is

$$
\nabla_\mu\psi
=\left(\partial_\mu+\frac14\omega_\mu{}^{ab}\gamma_{ab}\right)\psi,
\qquad
\gamma_{ab}=\frac12[\gamma_a,\gamma_b].
$$

Pages on spinor fields in curved spacetime will state the precise vielbein and gamma-matrix conventions again, because that is where sign errors reproduce like rabbits.

## Stress tensors and source variations

For matter coupled to a background metric,

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}
\frac{\delta S_{\mathrm m}}{\delta g^{\mu\nu}}.
$$

Equivalently,

$$
\delta S_{\mathrm m}
=-\frac12\int d^Dx\sqrt{|g|}\,
T_{\mu\nu}\delta g^{\mu\nu}.
$$

When the matter equations of motion hold and the matter action is diffeomorphism invariant,

$$
\nabla^\mu T_{\mu\nu}=0.
$$

In Lorentzian signature, with

$$
Z[g,J]=\int\mathcal D\Phi\,e^{iS[\Phi;g,J]},
$$

one has formally

$$
\langle T_{\mu\nu}(x)\rangle
=
\frac{2i}{\sqrt{|g|}}
\frac{\delta\log Z[g]}{\delta g^{\mu\nu}(x)}.
$$

In Euclidean signature, with $Z_E[g]=\int\mathcal D\Phi\,e^{-S_E}$ and the same stress-tensor variation convention for $S_E$,

$$
\langle T_{ij}(x)\rangle_E
=
\frac{2}{\sqrt{g_E}}
\frac{\delta\log Z_E[g]}{\delta g_E^{ij}(x)}.
$$

The trace is

$$
T^\mu{}_\mu=g^{\mu\nu}T_{\mu\nu}.
$$

In a classically Weyl-invariant theory the trace may vanish classically but acquire a quantum trace anomaly after renormalization.

## Einstein–Hilbert action and cosmological constant

The default gravitational action is

$$
S_{\mathrm{EH}}
=
\frac{1}{2\kappa_D^2}
\int_M d^Dx\sqrt{|g|}\,(R-2\Lambda),
\qquad
\kappa_D^2=8\pi G_D.
$$

Adding matter gives

$$
S=S_{\mathrm{EH}}+S_{\mathrm m}.
$$

Varying with respect to $g^{\mu\nu}$ gives

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}
=
\kappa_D^2T_{\mu\nu}.
$$

A maximally symmetric vacuum solution obeys

$$
R_{\mu\nu}=\frac{2\Lambda}{D-2}g_{\mu\nu}.
$$

Therefore AdS$_D$ with radius $L$ has

$$
\Lambda
=-\frac{(D-1)(D-2)}{2L^2},
$$

while de Sitter has the same magnitude with the opposite sign.

The mass dimension of the gravitational coupling is

$$
[\kappa_D^2]=2-D,
\qquad
[G_D]=2-D.
$$

This negative mass dimension for $D>2$ is the first power-counting hint that Einstein gravity is an effective field theory.

## Boundaries and extrinsic curvature

Let $\partial M$ be a non-null boundary with unit normal $n^\mu$. Define

$$
\varepsilon_n=n_\mu n^\mu=\pm1.
$$

The induced metric is

$$
h_{\mu\nu}=g_{\mu\nu}-\varepsilon_n n_\mu n_\nu.
$$

The extrinsic curvature is

$$
K_{\mu\nu}=h_\mu{}^\rho h_\nu{}^\sigma\nabla_\rho n_\sigma,
\qquad
K=h^{\mu\nu}K_{\mu\nu}.
$$

For Dirichlet boundary conditions on the induced metric, the Einstein–Hilbert action is supplemented by the Gibbons–Hawking–York term

$$
S_{\mathrm{GHY}}
=
\frac{1}{\kappa_D^2}
\int_{\partial M} d^{D-1}x\sqrt{|h|}\,K,
$$

with the normal orientation stated on the page where it is used. Reversing $n^\mu$ reverses $K$ and hence the GHY term.

For a timelike boundary, the unrenormalized Brown–York tensor is conventionally written as

$$
T^{ij}_{\mathrm{BY}}
=\frac{2}{\sqrt{|h|}}\frac{\delta S_{\mathrm{grav,on\ shell}}}{\delta h_{ij}}.
$$

In asymptotically AdS spacetimes this object is divergent before counterterms are added. The renormalized holographic stress tensor is obtained from the renormalized on-shell action,

$$
S_{\mathrm{ren}}=S_{\mathrm{bulk}}+S_{\mathrm{GHY}}+S_{\mathrm{ct}},
\qquad
T^{ij}_{\mathrm{ren}}
=\frac{2}{\sqrt{|\gamma|}}
\frac{\delta S_{\mathrm{ren}}}{\delta\gamma_{ij}},
$$

where $\gamma_{ij}$ is the cutoff-surface metric. Some references use the opposite sign because they vary $\gamma^{ij}$ instead of $\gamma_{ij}$, or choose the opposite outward normal.

## Euclidean continuation and thermal circles

The default Wick rotation for ordinary QFT is

$$
t=-i\tau,
\qquad
Z_L=\int\mathcal D\Phi\,e^{iS_L}
\longrightarrow
Z_E=\int\mathcal D\Phi\,e^{-S_E}.
$$

Euclidean metrics are positive definite unless stated otherwise. We write their determinant as $g_E$ and their volume element as

$$
d\mathrm{vol}_{g_E}=d^Dx\sqrt{g_E}.
$$

For thermal field theory,

$$
\tau\sim \tau+\beta,
\qquad
T=\beta^{-1}.
$$

Bosonic fields are periodic and fermionic fields are antiperiodic around the Euclidean thermal circle.

For stationary black holes, the Hawking temperature is obtained by demanding smoothness of the Euclidean near-horizon geometry. The result is

$$
T_H=\frac{\kappa}{2\pi},
$$

where $\kappa$ is the surface gravity of the horizon-generating Killing field.

Gravity has extra Euclidean sign subtleties: the conformal factor problem, boundary terms, and background subtraction/counterterm choices are not optional footnotes. Pages that use Euclidean gravity will state their on-shell action convention explicitly.

## AdS and Fefferman–Graham conventions

For Lorentzian AdS$_{d+1}$ in Poincare coordinates with mostly-minus signature, we write

$$
ds^2
=
\frac{L^2}{z^2}
\left(dt^2-d\mathbf x^2-dz^2\right),
\qquad
z>0.
$$

The conformal boundary is at $z=0$. Many references use mostly-plus signature and write the radial term with the opposite sign; this is a signature translation, not a physical disagreement.

Near an asymptotically AdS boundary, Fefferman–Graham gauge is written in Lorentzian mostly-minus form as

$$
ds^2
=
\frac{L^2}{z^2}
\left(g_{ij}(z,x)dx^i dx^j-dz^2\right),
$$

where $g_{(0)ij}(x)=g_{ij}(0,x)$ defines the boundary metric representative. In Euclidean signature, the same expression becomes positive definite and the radial term has a plus sign.

For a bulk scalar of mass $m$ in AdS$_{d+1}$, the dimension of the dual scalar primary is determined by

$$
\Delta(\Delta-d)=m^2L^2.
$$

The two roots are

$$
\Delta_\pm=\frac d2\pm
\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The standard quantization uses $\Delta=\Delta_+$ when no alternate quantization is stated.

## Black-hole thermodynamics conventions

A Killing horizon generated by $\chi^\mu$ has surface gravity $\kappa$ defined by

$$
\chi^\nu\nabla_\nu\chi^\mu=\kappa\chi^\mu
\quad\text{on the horizon}.
$$

The Hawking temperature is

$$
T_H=\frac{\kappa}{2\pi}.
$$

For Einstein gravity, the Bekenstein–Hawking entropy is

$$
S_{\mathrm{BH}}=\frac{A_H}{4G_D}.
$$

In higher-derivative gravity, this formula is replaced by Wald entropy. Pages on higher-curvature corrections will not silently use the area law.

The first law for a stationary charged rotating black hole is written schematically as

$$
dM=T_H\,dS+\Omega_H\,dJ+\Phi_H\,dQ,
$$

with the potentials normalized relative to the horizon generator and the asymptotic time coordinate used to define $M$.

## Common pitfalls

**Changing the Riemann sign but not the Einstein equation.** If $R^\rho{}_{\sigma\mu\nu}$ is reversed, $R_{\mu\nu}$ and $R$ reverse. The Einstein–Hilbert action and cosmological-constant interpretation must be translated consistently.

**Forgetting that mostly-minus makes spacelike radial directions negative in Lorentzian signature.** In this volume, Lorentzian AdS Poincare coordinates have $-dz^2$. Euclidean AdS has $+dz^2$.

**Using $\sqrt{-g}$ in every dimension without thinking.** With mostly-minus signature, the determinant sign depends on $D$. We therefore use $\sqrt{|g|}$ in general formulas.

**Confusing stress-tensor variation with respect to $g_{\mu\nu}$ and $g^{\mu\nu}$.** The sign changes. This is one of the fastest ways to corrupt a Ward identity.

**Forgetting boundary terms.** The Einstein–Hilbert action alone does not have a well-posed Dirichlet variational principle for the metric. The Gibbons–Hawking–York term is part of the classical setup, not a quantum correction.

**Treating Euclidean gravity as ordinary Wick-rotated scalar QFT.** Euclidean gravity has special issues: boundary terms, saddle choices, negative modes, and the conformal-factor problem.

## Relations to other pages

This page extends the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/) from flat-space QFT to curved backgrounds and dynamical geometry.

For the geometric language behind these formulas, read [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/). Later pages in this volume will specialize these conventions to QFT in curved spacetime, stress-tensor renormalization, semiclassical gravity, black holes, AdS boundary conditions, holographic renormalization, and thermal holography.

## Research status

The conventions themselves are not research questions. The physics they support is. Curved-spacetime QFT, semiclassical gravity, black-hole evaporation, holographic renormalization, and quantum-gravity constraints all depend on carefully separating convention-dependent signs from invariant statements.

The active frontier is not “which sign is right.” The active frontier is how to define observables, states, entropy, and renormalized stress tensors in regimes where global time, asymptotic particles, or a fixed background metric may be absent.

## Exercises

### Exercise 1: Translate the AdS cosmological constant

Using the Einstein equation in vacuum,

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}=0,
$$

show that AdS$_D$ with

$$
R_{\mu\nu}=-\frac{D-1}{L^2}g_{\mu\nu}
$$

requires

$$
\Lambda=-\frac{(D-1)(D-2)}{2L^2}.
$$

<details><summary><strong>Solution</strong></summary>

For a maximally symmetric vacuum with $R_{\mu\nu}=\lambda g_{\mu\nu}$, the scalar curvature is $R=D\lambda$. Therefore

$$
G_{\mu\nu}=R_{\mu\nu}-\frac12Rg_{\mu\nu}
=\left(1-\frac D2\right)\lambda g_{\mu\nu}.
$$

The vacuum Einstein equation gives

$$
\left(1-\frac D2\right)\lambda+\Lambda=0,
\qquad
\Lambda=\frac{D-2}{2}\lambda.
$$

For AdS, $\lambda=-(D-1)/L^2$, hence

$$
\Lambda=-\frac{(D-1)(D-2)}{2L^2}.
$$

</details>

### Exercise 2: Check the scalar equation of motion

Starting from

$$
S_\phi
=\frac12\int d^Dx\sqrt{|g|}\,
\left(g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-(m^2+\xi R)\phi^2\right),
$$

show that the equation of motion is

$$
(\Box_g+m^2+\xi R)\phi=0.
$$

<details><summary><strong>Solution</strong></summary>

Varying the scalar gives

$$
\delta S_\phi
=\int d^Dx\sqrt{|g|}\,
\left(g^{\mu\nu}\partial_\mu\phi\partial_\nu\delta\phi
-(m^2+\xi R)\phi\delta\phi\right).
$$

Integrating by parts and dropping the boundary term,

$$
\int d^Dx\sqrt{|g|}\,g^{\mu\nu}\partial_\mu\phi\partial_\nu\delta\phi
=
-\int d^Dx\sqrt{|g|}\,(\Box_g\phi)\delta\phi.
$$

Therefore

$$
\delta S_\phi
=-\int d^Dx\sqrt{|g|}\,
(\Box_g+m^2+\xi R)\phi\,\delta\phi.
$$

Since $\delta\phi$ is arbitrary, the stated equation follows.

</details>

### Exercise 3: Stress tensor sign check

Use

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}\frac{\delta S_m}{\delta g^{\mu\nu}}
$$

for a real scalar in flat spacetime to show that the energy density of a free massive scalar is positive:

$$
T_{00}=\frac12\dot\phi^2+\frac12(\nabla\phi)^2+\frac12m^2\phi^2.
$$

<details><summary><strong>Solution</strong></summary>

For

$$
\mathcal L=(1/2)\partial_\rho\phi\partial^\rho\phi-(1/2)m^2\phi^2,
$$

metric variation gives

$$
T_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L.
$$

In mostly-minus flat spacetime,

$$
\mathcal L
=\frac12\dot\phi^2-\frac12(\nabla\phi)^2-\frac12m^2\phi^2.
$$

Since $g_{00}=1$,

$$
T_{00}
=\dot\phi^2-\mathcal L
=(1/2)\dot\phi^2+(1/2)(\nabla\phi)^2+(1/2)m^2\phi^2.
$$

The sign convention therefore gives positive scalar energy density.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *General Relativity*, University of Chicago Press, 1984.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- E. Poisson, *A Relativist's Toolkit*, Cambridge University Press, 2004.
- M. Nakahara, *Geometry, Topology and Physics*, 2nd ed., CRC Press, 2018.
- T. Frankel, *The Geometry of Physics*, 3rd ed., Cambridge University Press, 2011.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Princeton University Press, 2010.
- S. Weinberg, *The Quantum Theory of Fields, Vol. I: Foundations*, Cambridge University Press, 1995.
- K. Skenderis, “Lecture notes on holographic renormalization,” *Classical and Quantum Gravity* **19** (2002) 5849.
- S. de Haro, K. Skenderis, and S. N. Solodukhin, “Holographic reconstruction of spacetime and renormalization in the AdS/CFT correspondence,” *Communications in Mathematical Physics* **217** (2001) 595.

## Version history

- 2026-07-01: Replaced the scaffold with a polished conventions page for curved-spacetime QFT, gravity, black holes, and holography.
