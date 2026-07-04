---
title: "Euclidean and Lorentzian Signatures"
description: "How Euclidean CFT correlators, Lorentzian real-time correlators, Wick rotation, i-epsilon prescriptions, reflection positivity, causality, thermal periodicity, and holographic boundary conditions fit together."
sidebar:
  order: 3
---

## The point of this page

Conformal field theory is usually easiest to formulate in Euclidean signature, but AdS/CFT is often most physical in Lorentzian signature. Euclidean CFT gives clean symmetry constraints, radial quantization, convergent path integrals, conformal blocks, and the operator product expansion. Lorentzian CFT gives causal propagation, commutators, real-time response, chaos, horizons, and black-hole physics.

A serious AdS/CFT reader must therefore be bilingual.

$$
\boxed{
\text{Euclidean CFT organizes the data. Lorentzian CFT reveals the causal physics.}
}
$$

The two languages are related by analytic continuation, but the continuation is not a harmless substitution $t=-i\tau$. One must specify operator orderings, branch choices, $i\epsilon$ prescriptions, and sometimes a real-time contour. Many mistakes in holography come from treating all correlators as if they were the same analytic function evaluated at different values of time.

This page explains the signatures carefully enough that later discussions of radial quantization, conformal blocks, thermal CFT, black holes, and real-time holography have a common foundation.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Analytic continuation between Euclidean and Lorentzian CFT correlators](/figures/cft/euclidean-lorentzian-continuation.svg)

<figcaption>

A Euclidean correlator is naturally defined in ordered Euclidean time domains. Lorentzian correlators are boundary values of the same analytic functions with specified $i\epsilon$ prescriptions. Coincidence singularities in Euclidean space become lightcone singularities, branch cuts, or poles in Lorentzian signature.

</figcaption>
</figure>

## Conventions

We use mostly-plus Lorentzian signature,

$$
\eta_{\mu\nu}=\mathrm{diag}(-,+,\ldots,+),
\qquad
x^\mu=(t,\mathbf x),
$$

so the Lorentzian interval is

$$
x_L^2=\eta_{\mu\nu}x^\mu x^\nu=-t^2+\mathbf x^2.
$$

Euclidean coordinates are

$$
x_E^\mu=(\tau,\mathbf x),
\qquad
x_E^2=\tau^2+\mathbf x^2.
$$

The basic Wick rotation is

$$
t=-i\tau,
\qquad
\tau=i t.
$$

Under this continuation,

$$
x_L^2=-(-i\tau)^2+
\mathbf x^2=\tau^2+
\mathbf x^2=x_E^2.
$$

This equality is the innocent-looking beginning of the Euclidean-Lorentzian dictionary. The non-innocent part is that correlation functions have singularities, so analytic continuation must say how those singularities are avoided.

## Wick rotation in the path integral

Consider a real scalar field in Lorentzian signature,

$$
S_L=\int dt\,d^{d-1}\mathbf x\,
\left[
\frac12(\partial_t\phi)^2
-\frac12(\nabla\phi)^2
-\frac12m^2\phi^2
\right].
$$

Set $t=-i\tau$, so $dt=-i\,d\tau$ and $\partial_t=i\partial_\tau$. Then

$$
S_L
=
-i\int d\tau\,d^{d-1}\mathbf x\,
\left[
-\frac12(\partial_\tau\phi)^2
-\frac12(\nabla\phi)^2
-\frac12m^2\phi^2
\right]
=iS_E,
$$

where

$$
S_E=\int d\tau\,d^{d-1}\mathbf x\,
\left[
\frac12(\partial_\tau\phi)^2
+\frac12(\nabla\phi)^2
+\frac12m^2\phi^2
\right].
$$

Thus the oscillatory Lorentzian weight becomes the exponentially damped Euclidean weight:

$$
e^{iS_L}\longrightarrow e^{-S_E}.
$$

This is why Euclidean path integrals are often better-defined. The Euclidean action is bounded below in many theories where the Lorentzian phase $e^{iS_L}$ is only conditionally meaningful. Perturbation theory, instantons, lattice regularization, and many nonperturbative definitions are therefore naturally Euclidean.

But the phrase “many theories” is doing work. Gauge theories require gauge fixing and ghosts; fermions require Grassmann variables; real-time nonequilibrium observables require more than a Euclidean partition function; and gravitational path integrals are subtle because the Euclidean Einstein action is not simply positive. Still, for CFT kinematics and local operator data, Euclidean signature is the cleanest starting point.

> **AdS/CFT checkpoint.** Euclidean AdS calculations compute Euclidean CFT correlators by imposing regularity in the interior. Lorentzian AdS calculations require causal boundary conditions: Feynman, retarded, advanced, or Schwinger-Keldysh. The same bulk equation can therefore compute different CFT correlators depending on the contour and boundary conditions.

## Euclidean correlators: Schwinger functions

Euclidean correlation functions are often called Schwinger functions. For local operators $\mathcal O_i$, define

$$
G_E(x_1,\ldots,x_n)
=
\langle
\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)
\rangle_E.
$$

In a path-integral representation,

$$
G_E(x_1,\ldots,x_n)
=
\frac{1}{Z_E}
\int [D\varphi]\,
\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)
\,e^{-S_E[\varphi]}.
$$

For bosonic local operators at separated Euclidean points, there is no time-ordering ambiguity in the same sense as Lorentzian time. The Euclidean path integral computes the correlator with insertions at specified Euclidean positions. If one chooses a Euclidean time coordinate $\tau$, then canonical quantization rewrites the same object as a Euclidean-time-ordered matrix element.

For example, for $\tau_1>\tau_2$,

$$
\langle \mathcal O_E(\tau_1,\mathbf x_1)\mathcal O_E(\tau_2,\mathbf x_2)\rangle
=
\langle 0|
\mathcal O_E(\tau_1,\mathbf x_1)
\mathcal O_E(\tau_2,\mathbf x_2)
|0\rangle,
$$

with

$$
\mathcal O_E(\tau,\mathbf x)=e^{\tau H}\mathcal O(0,\mathbf x)e^{-\tau H}.
$$

This is related to the Lorentzian Heisenberg operator

$$
\mathcal O_L(t,\mathbf x)=e^{iHt}\mathcal O(0,\mathbf x)e^{-iHt}
$$

by

$$
\mathcal O_E(\tau,\mathbf x)=\mathcal O_L(-i\tau,\mathbf x).
$$

The Euclidean correlator is therefore an analytic continuation of a Lorentzian object, but only inside a domain where the spectral sum converges.

## Lorentzian correlators: orderings matter

Lorentzian signature has several inequivalent correlation functions. For two bosonic operators, the most common are:

$$
G^+(x)=\langle 0|\mathcal O(x)\mathcal O(0)|0\rangle,
$$

$$
G^-(x)=\langle 0|\mathcal O(0)\mathcal O(x)|0\rangle,
$$

$$
G_F(x)=\langle 0|T\{\mathcal O(x)\mathcal O(0)\}|0\rangle,
$$

$$
G_R(x)=-i\theta(t)\langle 0|[\mathcal O(x),\mathcal O(0)]|0\rangle,
$$

$$
G_A(x)=i\theta(-t)\langle 0|[\mathcal O(x),\mathcal O(0)]|0\rangle.
$$

Here $G^+$ and $G^-$ are Wightman functions, $G_F$ is the Feynman or time-ordered correlator, and $G_R$, $G_A$ are retarded and advanced correlators. They are not the same object.

The retarded correlator is especially important in finite-temperature and black-hole physics because it measures linear response. If a source $J$ perturbs the Hamiltonian by

$$
\delta H(t)=-\int d^{d-1}\mathbf x\,J(t,\mathbf x)\mathcal O(t,\mathbf x),
$$

then, to first order,

$$
\delta\langle \mathcal O(t,\mathbf x)\rangle
=
\int dt'\,d^{d-1}\mathbf x'\,
G_R(t-t',\mathbf x-
\mathbf x')J(t',\mathbf x').
$$

The step function in $G_R$ implements causality: a perturbation at time $t'$ cannot affect an expectation value at an earlier time $t<t'$.

> **AdS/CFT checkpoint.** In a black-hole background, retarded CFT correlators are computed by imposing infalling boundary conditions at the horizon. This prescription is not visible in a purely Euclidean calculation until one analytically continues carefully.

## The $i\epsilon$ prescription

The $i\epsilon$ prescription tells us how Lorentzian time approaches the singularities of a Euclidean correlator.

For a Euclidean two-point function with $\tau>0$,

$$
G_E(\tau,\mathbf x)
=
\langle 0|\mathcal O_E(\tau,\mathbf x)\mathcal O_E(0)|0\rangle,
$$

the spectral representation has the schematic form

$$
G_E(\tau,\mathbf x)
=
\sum_n e^{-E_n\tau}
\langle 0|\mathcal O(0,\mathbf x)|n\rangle
\langle n|\mathcal O(0)|0\rangle.
$$

This converges for $\mathrm{Re}\,\tau>0$. The Wightman function is the boundary value

$$
G^+(t,\mathbf x)
=
\lim_{\epsilon\to0^+}G_E(\epsilon+i t,\mathbf x).
$$

Equivalently, one may say that the Lorentzian time is shifted as

$$
t\to t-i\epsilon.
$$

This small imaginary part is not decoration. It is what remembers the operator ordering.

For a scalar primary operator of dimension $\Delta$, the Euclidean two-point function is

$$
G_E(\tau,\mathbf x)
=
\frac{C_{\mathcal O}}{(\tau^2+\mathbf x^2)^\Delta}.
$$

The Wightman function obtained from $\tau=\epsilon+i t$ is

$$
G^+(t,\mathbf x)
=
\lim_{\epsilon\to0^+}
\frac{C_{\mathcal O}}
{\left[\mathbf x^2-(t-i\epsilon)^2\right]^\Delta}.
$$

Similarly,

$$
G^-(t,\mathbf x)
=
\lim_{\epsilon\to0^+}
\frac{C_{\mathcal O}}
{\left[\mathbf x^2-(t+i\epsilon)^2\right]^\Delta}.
$$

The time-ordered correlator is

$$
G_F(t,\mathbf x)
=
\theta(t)G^+(t,\mathbf x)+\theta(-t)G^-(t,\mathbf x).
$$

For spacelike separation,

$$
\mathbf x^2-t^2>0,
$$

the denominator does not cross a branch cut as $\epsilon\to0$, so $G^+=G^-$ for identical bosonic scalar operators. The commutator therefore vanishes at spacelike separation:

$$
[\mathcal O(t,\mathbf x),\mathcal O(0)]=0,
\qquad
\mathbf x^2-t^2>0.
$$

For timelike separation,

$$
t^2-\mathbf x^2>0,
$$

the two boundary values generally differ by a phase or a pole prescription. This difference is the Lorentzian causal singularity structure.

## Why Euclidean CFT is so powerful

Euclidean CFT has three major advantages.

First, the conformal group acts geometrically on Euclidean space. In $d$ Euclidean dimensions, the conformal group is locally $SO(d+1,1)$. Correlation functions are constrained by rotations, translations, dilatations, and special conformal transformations. For scalar primary operators,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle_E
=
\frac{C_i\delta_{ij}}{|x|^{2\Delta_i}}
$$

in an orthonormal basis.

Second, the Euclidean OPE is naturally convergent inside spheres. If $|x|$ is small compared to the distance to other insertions,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\,|x|^{\Delta_k-\Delta_i-\Delta_j}
\mathcal O_k(0)+\text{descendants}.
$$

The Euclidean geometry makes the convergence statement precise using radial quantization.

Third, Euclidean four-point functions are the cleanest arena for crossing symmetry. For identical scalar operators,

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta}x_{34}^{2\Delta}}\,\mathcal G(u,v),
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The equality of different OPE decompositions gives crossing equations. This is the modern conformal bootstrap in its cleanest form.

## Why Lorentzian CFT is indispensable

Euclidean CFT organizes the operator algebra, but Lorentzian CFT knows about causal propagation. Several central concepts in holography are intrinsically Lorentzian:

$$
\begin{array}{ccl}
\text{microcausality} &:& [\mathcal O(x),\mathcal O(y)]=0 \text{ for spacelike separation},\\[3pt]
\text{linear response} &:& G_R \text{ determines response to sources},\\[3pt]
\text{chaos} &:& \text{out-of-time-order correlators require real-time ordering},\\[3pt]
\text{black holes} &:& \text{horizons impose causal boundary conditions},\\[3pt]
\text{bulk locality} &:& \text{encoded in Lorentzian singularities and commutators}.
\end{array}
$$

A Euclidean four-point function may be analytically continued to Lorentzian configurations in many inequivalent ways. These continuations correspond to different operator orderings. In particular, out-of-time-order correlators are obtained by taking operators around branch points in complexified cross-ratio space. This is why Lorentzian analytic structure is central in modern work on chaos, causality bounds, and bulk locality.

A good rule of thumb is:

$$
\boxed{
\text{Euclidean crossing constrains consistency; Lorentzian singularities diagnose causality and locality.}
}
$$

## Reflection positivity and unitarity

Not every Euclidean-looking set of correlation functions defines a unitary Lorentzian QFT. The Euclidean data must obey reflection positivity.

Choose a Euclidean time coordinate $\tau$ and define time reflection

$$
\Theta:(\tau,\mathbf x)\mapsto(-\tau,\mathbf x).
$$

For a scalar operator, reflection acts schematically as

$$
\Theta\mathcal O(\tau,\mathbf x)=\mathcal O^\dagger(-\tau,\mathbf x).
$$

For any finite linear combination of operator insertions supported at positive Euclidean time,

$$
F=\sum_i c_i\mathcal O_i(\tau_i,\mathbf x_i),
\qquad
\tau_i>0,
$$

reflection positivity requires

$$
\langle (\Theta F)F\rangle_E\ge0.
$$

This condition reconstructs a positive-norm Hilbert space after Wick rotation. In CFT language, it is the Euclidean origin of unitarity. Later, when we derive unitarity bounds such as

$$
\Delta\ge \frac{d-2}{2}
$$

for scalar primaries in $d$ dimensions, we are using the same principle in radial quantization.

> **AdS/CFT checkpoint.** Bulk ghost fields or wrong-sign kinetic terms would show up on the boundary as violations of reflection positivity or negative-norm states. Boundary unitarity is therefore one of the sharpest nonperturbative tests of whether a proposed bulk theory can be holographic.

## Radial quantization: Euclidean signature as a Hilbert-space machine

Euclidean CFT has a special quantization adapted to conformal symmetry. Instead of taking time slices at fixed $\tau$, take spheres centered at the origin.

Write

$$
r=|x|,
\qquad
\rho=\log r.
$$

The flat Euclidean metric becomes

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
=e^{2\rho}\left(d\rho^2+d\Omega_{d-1}^2\right).
$$

A CFT is insensitive to the Weyl factor $e^{2\rho}$ up to possible anomalies, so Euclidean space minus the origin is conformally equivalent to the cylinder:

$$
\mathbb R^d\setminus\{0\}
\quad\longleftrightarrow\quad
\mathbb R_\rho\times S^{d-1}.
$$

The dilatation generator $D$ becomes the Hamiltonian on the cylinder:

$$
H_{\rm cyl}=D.
$$

A local operator at the origin creates a state on the sphere:

$$
\mathcal O(0)|0\rangle
\quad\longleftrightarrow\quad
|\mathcal O\rangle.
$$

If $\mathcal O$ is a primary operator of dimension $\Delta$, then

$$
D|\mathcal O\rangle=\Delta |\mathcal O\rangle.
$$

Thus scaling dimensions are energies in radial quantization.

This is a Euclidean construction, but it has direct holographic meaning. Global AdS has a natural time coordinate whose boundary is $\mathbb R\times S^{d-1}$. The CFT cylinder energy is the global AdS energy. Therefore

$$
\boxed{
\text{CFT scaling dimension }\Delta
\quad\leftrightarrow\quad
\text{global AdS energy.}
}
$$

This is one of the deepest reasons Euclidean radial quantization is not merely a technical convenience.

## Thermal field theory and the KMS condition

Finite temperature is another place where Euclidean and Lorentzian languages meet beautifully.

A thermal density matrix is

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
Z(\beta)=\mathrm{Tr}\,e^{-\beta H},
$$

where $\beta=1/T$. The Euclidean path-integral representation has periodic Euclidean time:

$$
\tau\sim \tau+\beta
$$

for bosonic operators, and antiperiodic Euclidean time for fermionic fields.

Thermal Lorentzian correlators obey the Kubo-Martin-Schwinger relation. For bosonic operators,

$$
G^>(t)=\langle \mathcal O(t)\mathcal O(0)\rangle_\beta,
\qquad
G^<(t)=\langle \mathcal O(0)\mathcal O(t)\rangle_\beta,
$$

and the KMS condition is

$$
G^>(t-i\beta)=G^<(t).
$$

This is the Lorentzian shadow of Euclidean periodicity. In holography, the same periodicity appears as smoothness of the Euclidean black-hole geometry at the horizon. The inverse temperature is fixed by avoiding a conical singularity.

> **AdS/CFT checkpoint.** Euclidean black holes compute thermal partition functions and Euclidean correlators. Real-time dissipation, quasinormal modes, transport, and absorption require Lorentzian continuation and retarded correlators.

## Sources in Euclidean and Lorentzian signature

The source functional also changes its appearance between signatures.

In Euclidean signature, with source $J_E$, one often writes

$$
Z_E[J_E]
=
\left\langle
\exp\left(\int d^d x_E\,J_E(x)\mathcal O(x)\right)
\right\rangle_E.
$$

In Lorentzian signature, the corresponding generating functional is schematically

$$
Z_L[J_L]
=
\left\langle
\exp\left(i\int d^d x_L\,J_L(x)\mathcal O(x)\right)
\right\rangle_L.
$$

The factor of $i$ is the same one that appears in $e^{iS_L}$. For in-out correlators, this gives Feynman ordering. For real-time response in a state, one usually needs an in-in or Schwinger-Keldysh contour with two sources $J_+$ and $J_-$:

$$
Z_{\rm SK}[J_+,J_-].
$$

Functional derivatives with respect to $J_+$ and $J_-$ generate different real-time orderings. This is the field-theory origin of the multiple Lorentzian prescriptions in holography.

The Euclidean relation

$$
Z_{\rm CFT}^{E}[J]
=
Z_{\rm bulk}^{E}[\phi_{\partial}=J]
$$

is therefore not the whole real-time story. It is the cleanest starting point, but Lorentzian questions require the correct Lorentzian contour.


## The conformal group in the two signatures

The conformal algebra is usually written differently in Euclidean and Lorentzian signature.

In Euclidean $d$-dimensional CFT, the conformal group is locally

$$
SO(d+1,1).
$$

In Lorentzian $d$-dimensional CFT, it is locally

$$
SO(d,2).
$$

This difference is not cosmetic. The Lorentzian group has causal structure built into its real form, while the Euclidean group acts on the conformal compactification of $\mathbb R^d$. But the complexified Lie algebras agree. This is why many representation-theoretic statements can be derived in Euclidean signature and then continued to Lorentzian signature.

For AdS/CFT, the Lorentzian statement is especially direct:

$$
\mathrm{Isom}(AdS_{d+1})=SO(d,2),
$$

which matches the Lorentzian conformal group of the boundary CFT. Euclidean AdS, often called hyperbolic space $H_{d+1}$, has isometry group

$$
\mathrm{Isom}(H_{d+1})=SO(d+1,1),
$$

which matches the Euclidean conformal group. Thus both signatures know the same holographic symmetry, but as different real slices of a complexified structure.

This becomes important when we discuss representations. Euclidean radial quantization naturally gives a Hilbert space on $S^{d-1}$ with Hamiltonian $D$. Lorentzian quantization gives physical time evolution, commutators, and causal diamonds. The same operator $\mathcal O$ participates in both stories, but the reality conditions and allowed orderings differ.

## Momentum-space continuation

Real-time physics is often described in momentum space. The Euclidean frequency variable is discrete at finite temperature and continuous at zero temperature. The Lorentzian frequency variable carries an $i\epsilon$ prescription.

At zero temperature, a Euclidean two-point function may be written as

$$
G_E(\omega_E,\mathbf k)
=
\int d\tau\,d^{d-1}\mathbf x\,
e^{-i\omega_E\tau-i\mathbf k\cdot\mathbf x}
G_E(\tau,\mathbf x).
$$

The retarded correlator is obtained by continuing to the upper half of the Lorentzian frequency plane:

$$
G_R(\omega,\mathbf k)
=
G_E(\omega_E=-i(\omega+i0^+),\mathbf k),
$$

up to convention-dependent signs in the Fourier transform. Equivalently, many physicists write the same rule as

$$
i\omega_E\to \omega+i0^+.
$$

The imaginary part of $G_R$ defines the spectral density,

$$
\rho(\omega,\mathbf k)=-2\,\mathrm{Im}\,G_R(\omega,\mathbf k),
$$

again up to sign conventions. The spectral density measures the density of states weighted by the operator $\mathcal O$. In holography it is related to absorption by the bulk geometry. For example, poles of $G_R$ in thermal states correspond to quasinormal modes of black holes.

At finite temperature, Euclidean frequencies are Matsubara frequencies,

$$
\omega_n=\frac{2\pi n}{\beta}
$$

for bosonic operators. Euclidean data gives values of $G_E(i\omega_n,\mathbf k)$ at discrete points. The retarded correlator is the analytic function whose boundary value at real frequency has the correct upper-half-plane analyticity and agrees with the Euclidean data at Matsubara points. This extra analytic requirement is essential.

## Lorentzian cross-ratios and branch choices

For Euclidean four-point functions, the conformal cross-ratios $u,v$ are often real in a convenient configuration. Lorentzian continuation complexifies them. Different real-time orderings correspond to different paths around branch points.

For identical scalar operators,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
\sim
\mathcal G(u,v).
$$

In Euclidean signature, the OPE limit $x_1\to x_2$ is usually associated with

$$
u\to0,
\qquad
v\to1.
$$

In Lorentzian signature, the same algebraic values of $u,v$ do not determine the correlator until we specify how each operator time is shifted:

$$
t_i\to t_i-i\epsilon_i.
$$

Different orderings correspond to different relative choices of $\epsilon_i$. This is why the Lorentzian continuation of a Euclidean conformal block is not merely a plug-in operation. It is a choice of sheet of a multivalued analytic function.

This sheet structure is the foundation of several modern ideas: the lightcone bootstrap, Regge limits, causality constraints, averaged null energy, and chaos bounds. In holography, these same analytic continuations know whether a bulk signal can propagate causally through AdS.

## A compact dictionary

| Question | Euclidean answer | Lorentzian answer | Holographic use |
|---|---|---|---|
| What are basic correlators? | Schwinger functions | Wightman, Feynman, retarded, advanced | Different bulk boundary conditions |
| What is time? | Euclidean ordering or radial time | Physical causal time | Global AdS time, black-hole time |
| What ensures unitarity? | Reflection positivity | Positive-norm Hilbert space | No bulk ghosts |
| Where are singularities? | Coincident points | Lightcones and branch cuts | Bulk propagation and locality |
| What computes thermal physics? | Circle of length $\beta$ | KMS relation and response | Euclidean black holes, retarded transport |
| What is easiest for bootstrap? | OPE convergence and crossing | Causality, Regge limits, chaos | Locality bounds and gravitational causality |

## Common mistakes

The first mistake is to write $t=-i\tau$ and stop. This loses the $i\epsilon$ prescription, and therefore loses operator ordering.

The second mistake is to assume that a Euclidean correlator automatically defines a unitary Lorentzian theory. Reflection positivity is an extra condition, not a poetic slogan.

The third mistake is to treat retarded correlators as analytic continuations of Euclidean correlators without specifying the correct boundary value. At finite temperature, the retarded correlator is obtained from the Euclidean Matsubara correlator by a specific continuation of discrete frequencies,

$$
i\omega_n\to \omega+i0^+,
$$

not by an arbitrary replacement.

The fourth mistake is to ignore operator ordering in Lorentzian four-point functions. Different paths around branch points in complexified cross-ratio space produce different real-time correlators. This is not a technical nuisance; it is the origin of chaos diagnostics and causality constraints.

## What to remember

Euclidean CFT is the natural home of conformal symmetry, the OPE, radial quantization, reflection positivity, and crossing equations.

Lorentzian CFT is the natural home of causality, commutators, response functions, lightcone singularities, and black-hole physics.

The bridge between them is analytic continuation with a specified prescription:

$$
\text{Euclidean correlator}
\quad
\overset{i\epsilon\text{ and ordering}}{\longrightarrow}
\quad
\text{Lorentzian correlator}.
$$

For AdS/CFT, the practical moral is:

$$
\boxed{
\text{Always ask which correlator you are computing before solving the bulk problem.}
}
$$

## Exercises

### Exercise 1. Wick rotation of the scalar action

Start from the Lorentzian scalar action in mostly-plus signature,

$$
S_L=\int dt\,d^{d-1}\mathbf x\,
\left[
\frac12(\partial_t\phi)^2
-\frac12(\nabla\phi)^2
-\frac12m^2\phi^2
\right].
$$

Use $t=-i\tau$ to derive the Euclidean action $S_E$ and show that $e^{iS_L}\to e^{-S_E}$.

<details>
<summary><strong>Solution</strong></summary>

With $t=-i\tau$, we have $dt=-i\,d\tau$ and $\partial_t=i\partial_\tau$. Therefore

$$
(\partial_t\phi)^2=- (\partial_\tau\phi)^2.
$$

Substitution gives

$$
S_L
=
\int (-i\,d\tau)d^{d-1}\mathbf x\,
\left[
-\frac12(\partial_\tau\phi)^2
-\frac12(\nabla\phi)^2
-\frac12m^2\phi^2
\right].
$$

Thus

$$
S_L=i\int d\tau\,d^{d-1}\mathbf x\,
\left[
\frac12(\partial_\tau\phi)^2
+\frac12(\nabla\phi)^2
+\frac12m^2\phi^2
\right]
=iS_E.
$$

Hence

$$
e^{iS_L}=e^{i(iS_E)}=e^{-S_E}.
$$

</details>

### Exercise 2. Continue a scalar CFT two-point function

A scalar primary in Euclidean signature has

$$
G_E(\tau,\mathbf x)=\frac{C}{(\tau^2+\mathbf x^2)^\Delta}.
$$

Use $\tau=\epsilon+i t$ to derive the Wightman function $G^+(t,\mathbf x)$. Then explain why the commutator vanishes for spacelike separation.

<details>
<summary><strong>Solution</strong></summary>

Set

$$
\tau=\epsilon+i t,
\qquad
\epsilon>0.
$$

Then

$$
\tau^2+\mathbf x^2
=(\epsilon+i t)^2+\mathbf x^2
=\mathbf x^2-t^2+2i\epsilon t+O(\epsilon^2)
=\mathbf x^2-(t-i\epsilon)^2+O(\epsilon^2).
$$

Therefore

$$
G^+(t,\mathbf x)
=
\lim_{\epsilon\to0^+}
\frac{C}{\left[\mathbf x^2-(t-i\epsilon)^2\right]^\Delta}.
$$

The opposite Wightman ordering gives

$$
G^-(t,\mathbf x)
=
\lim_{\epsilon\to0^+}
\frac{C}{\left[\mathbf x^2-(t+i\epsilon)^2\right]^\Delta}.
$$

For spacelike separation, $\mathbf x^2-t^2>0$. The denominator approaches a positive real number from either side, so the two boundary values agree:

$$
G^+(t,\mathbf x)=G^-(t,\mathbf x).
$$

Thus

$$
\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle=0
$$

at spacelike separation, as required by microcausality.

</details>

### Exercise 3. Reflection positivity from the spectral representation

Let $\mathcal O$ be a Hermitian scalar operator, and suppose $\tau>0$. Show that

$$
\langle \mathcal O(-\tau,\mathbf x)\mathcal O(\tau,\mathbf x)\rangle_E\ge0
$$

in a unitary theory.

<details>
<summary><strong>Solution</strong></summary>

Using Euclidean time evolution,

$$
\mathcal O_E(\tau)=e^{\tau H}\mathcal O(0)e^{-\tau H}.
$$

Then

$$
\mathcal O_E(\tau)|0\rangle
$$

is a state. Reflection maps the insertion at $\tau$ to one at $-\tau$, so the reflected correlator is the norm of this state:

$$
\langle \mathcal O_E(-\tau)\mathcal O_E(\tau)\rangle_E
=
\langle 0|\mathcal O_E(\tau)^\dagger\mathcal O_E(\tau)|0\rangle
=\|\mathcal O_E(\tau)|0\rangle\|^2\ge0.
$$

Equivalently, insert a complete set of Hamiltonian eigenstates:

$$
\langle \mathcal O_E(-\tau)\mathcal O_E(\tau)\rangle_E
=
\sum_n e^{-2\tau(E_n-E_0)}
|\langle n|\mathcal O|0\rangle|^2\ge0.
$$

This is the simplest form of reflection positivity.

</details>

### Exercise 4. Thermal periodicity and the KMS condition

For a bosonic operator in a thermal state, define

$$
G^>(t)=\frac{1}{Z}\mathrm{Tr}\left(e^{-\beta H}\mathcal O(t)\mathcal O(0)\right),
$$

$$
G^<(t)=\frac{1}{Z}\mathrm{Tr}\left(e^{-\beta H}\mathcal O(0)\mathcal O(t)\right).
$$

Show that

$$
G^>(t-i\beta)=G^<(t).
$$

<details>
<summary><strong>Solution</strong></summary>

Using $\mathcal O(t)=e^{iHt}\mathcal O(0)e^{-iHt}$,

$$
\mathcal O(t-i\beta)
=e^{iH(t-i\beta)}\mathcal O(0)e^{-iH(t-i\beta)}
=e^{iHt}e^{\beta H}\mathcal O(0)e^{-\beta H}e^{-iHt}.
$$

Then

$$
G^>(t-i\beta)
=\frac{1}{Z}\mathrm{Tr}\left(e^{-\beta H}\mathcal O(t-i\beta)\mathcal O(0)\right).
$$

Substitute the expression above:

$$
G^>(t-i\beta)
=\frac{1}{Z}\mathrm{Tr}\left(
\mathcal O(t)e^{-\beta H}\mathcal O(0)
\right).
$$

Using cyclicity of the trace,

$$
G^>(t-i\beta)
=\frac{1}{Z}\mathrm{Tr}\left(
e^{-\beta H}\mathcal O(0)\mathcal O(t)
\right)=G^<(t).
$$

This is the KMS relation. In Euclidean language, it is the statement that bosonic thermal correlators are periodic under $\tau\to\tau+\beta$.

</details>

### Exercise 5. Cylinder energy from scaling dimension

Use the map $r=e^\rho$ to show that flat space is conformal to the cylinder, and explain why a primary operator of dimension $\Delta$ creates a cylinder state of energy $\Delta$.

<details>
<summary><strong>Solution</strong></summary>

In polar coordinates on $\mathbb R^d$,

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2.
$$

Set $r=e^\rho$. Then $dr=e^\rho d\rho$, so

$$
ds^2=e^{2\rho}\left(d\rho^2+d\Omega_{d-1}^2\right).
$$

A CFT is invariant under Weyl rescalings up to possible anomalies, so $\mathbb R^d\setminus\{0\}$ is conformally equivalent to $\mathbb R_\rho\times S^{d-1}$.

Translations in $\rho$ correspond to scale transformations in $r$:

$$
\rho\to \rho+a
\quad\Longleftrightarrow\quad
r\to e^a r.
$$

Therefore the Hamiltonian generating cylinder time $\rho$ is the dilatation operator $D$:

$$
H_{\rm cyl}=D.
$$

If $\mathcal O$ is a primary of dimension $\Delta$, then

$$
D\mathcal O(0)|0\rangle=\Delta\mathcal O(0)|0\rangle.
$$

Hence the state created by $\mathcal O$ has cylinder energy $\Delta$.

</details>

## Further reading

For QFT preliminaries, Euclidean path integrals, correlation functions, and Ward identities, see the early chapters of Di Francesco, Mathieu, and Senechal. For modern higher-dimensional CFT, see Rychkov's lecture notes and Simmons-Duffin's TASI lectures. For Lorentzian correlators in holography, the essential topics are real-time finite-temperature field theory, Schwinger-Keldysh contours, and the Son-Starinets prescription for retarded correlators.
