---
title: "Lorentzian Correlators"
description: "Analytic continuation, i epsilon prescriptions, Wightman functions, retarded correlators, spectral density, and causality in CFT."
sidebar:
  order: 4
---

## Goal

Euclidean CFT is beautifully rigid. Conformal symmetry fixes two- and three-point functions, packages four-point functions into functions of cross-ratios, and makes the OPE a sharply convergent expansion in radial quantization. But AdS/CFT is ultimately a statement about a real-time quantum theory as well. Boundary sources can be turned on at real Lorentzian time. Bulk signals propagate causally. Black holes absorb perturbations. Thermal states have retarded response and quasinormal modes. Entanglement wedges, shock waves, Regge limits, and chaos are all Lorentzian questions.

The goal of this page is to explain how Lorentzian CFT correlators are obtained from Euclidean correlators, why the $i\epsilon$ prescription is not a harmless decoration, and how the different real-time correlators encode causality and spectral information.

The key message is:

$$
\text{Euclidean correlator}
\quad + \quad
\text{choice of analytic continuation sheet}
\quad = \quad
\text{Lorentzian correlator with a definite operator ordering}.
$$

This page is not yet about conformal blocks or the Lorentzian inversion formula. Those come later. Here we build the basic real-time dictionary.

## Conventions

We work in $d$ Lorentzian spacetime dimensions with mostly-plus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(-,+,\ldots,+),
$$

so that

$$
x^2=-t^2+\mathbf x^2,
\qquad
x_{ij}^2=-(t_i-t_j)^2+|\mathbf x_i-\mathbf x_j|^2.
$$

The corresponding Euclidean coordinate is

$$
x_E=(\tau,\mathbf x),
\qquad
x_E^2=\tau^2+\mathbf x^2.
$$

Analytic continuation is implemented by complexifying Euclidean time:

$$
\tau=\epsilon+i t.
$$

Equivalently, the complex Lorentzian time variable is

$$
z=t-i\epsilon.
$$

The small real parameters $\epsilon_i$ attached to operator insertions are not physical time delays. They encode operator ordering.

For a Wightman correlator ordered as

$$
\langle \mathcal O_1(t_1,\mathbf x_1)\mathcal O_2(t_2,\mathbf x_2)\cdots \mathcal O_n(t_n,\mathbf x_n)\rangle,
$$

one takes

$$
\epsilon_1>\epsilon_2>\cdots>\epsilon_n>0
$$

and then sends all $\epsilon_i$ to zero after the continuation. The real times $t_i$ may have any order. The vertical ordering in complex time is what remembers the operator ordering.

<figure class="doc-figure" style="--figure-width: 38rem; --caption-width: 55rem;">

![Complexified Lorentzian time and the i epsilon prescription](/figures/cft/lorentzian-iepsilon-prescription.svg)

<figcaption>

Analytic continuation to Lorentzian time. For the Wightman ordering $\mathcal O_1\mathcal O_2\mathcal O_3$, one evaluates the Euclidean correlator at $\tau_i=\epsilon_i+i t_i$, equivalently $z_i=t_i-i\epsilon_i$, with $\epsilon_1>\epsilon_2>\epsilon_3$. The real-time order of the numbers $t_i$ is independent of this operator ordering.

</figcaption>
</figure>

## Euclidean correlators as analytic functions

A Euclidean correlator is initially defined for real Euclidean insertion points:

$$
G_E(x_{1,E},\ldots,x_{n,E})
=
\langle \mathcal O_1(x_{1,E})\cdots \mathcal O_n(x_{n,E})\rangle_E.
$$

For separated points, it can often be regarded as the boundary value of an analytic function of complexified coordinates. Lorentzian correlators arise by approaching real Lorentzian points from different directions in this complex domain.

The cleanest rule is the following. The Lorentzian Wightman correlator with the displayed operator order is

$$
G_L^{(1\cdots n)}
=
\lim_{\epsilon_1>\cdots>\epsilon_n\to 0^+}
G_E(\tau_i=\epsilon_i+i t_i,\mathbf x_i).
$$

Different choices of the ordering of the $\epsilon_i$ give different Lorentzian boundary values. This matters because Euclidean CFT correlators have singularities when points become null-separated after continuation. Around these singularities, the analytic function has branch cuts or poles. Lorentzian physics is the physics of those sheets.

This is why the phrase “the Lorentzian correlator” is incomplete. One should specify the ordering:

$$
\text{Wightman},
\qquad
\text{time-ordered},
\qquad
\text{anti-time-ordered},
\qquad
\text{retarded},
\qquad
\text{advanced},
\qquad
\text{out-of-time-ordered}.
$$

All are related, but they are not the same object.

## The scalar two-point function

Let $\mathcal O$ be a scalar primary of dimension $\Delta$. In Euclidean signature,

$$
\langle \mathcal O(\tau,\mathbf x)\mathcal O(0)\rangle_E
=
\frac{C_{\mathcal O}}{(\tau^2+\mathbf x^2)^\Delta}.
$$

Continue using $\tau=\epsilon+i t$. The ordered Wightman function

$$
G^>(t,\mathbf x)
=
\langle \mathcal O(t,\mathbf x)\mathcal O(0)\rangle
$$

is

$$
G^>(t,\mathbf x)
=
\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t-i0)^2\right]^\Delta}.
$$

The oppositely ordered Wightman function

$$
G^<(t,\mathbf x)
=
\langle \mathcal O(0)\mathcal O(t,\mathbf x)\rangle
$$

is

$$
G^<(t,\mathbf x)
=
\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t+i0)^2\right]^\Delta}.
$$

These two expressions differ only in the sign of $i0$, but that sign determines the side of the branch cut. When $\mathbf x^2-t^2>0$, the separation is spacelike and the denominator stays away from the negative real axis. Then

$$
G^>(t,\mathbf x)=G^<(t,\mathbf x)
\qquad
\text{for spacelike separation}.
$$

When $t^2-\mathbf x^2>0$, the separation is timelike. The denominator crosses the branch cut of the complex power. The two Wightman functions can then differ.

For non-integer $\Delta$ and separated timelike points, one obtains the schematic discontinuity

$$
G^>(t,\mathbf x)-G^<(t,\mathbf x)
=
-2i C_{\mathcal O}\sin(\pi\Delta)\,
\operatorname{sgn}(t)\,
\theta(t^2-\mathbf x^2)
\frac{1}{(t^2-\mathbf x^2)^\Delta}.
$$

For integer or half-integer dimensions, this formula should be understood by analytic continuation in $\Delta$. The discontinuity may collapse partly or entirely to distributions supported on the light cone. This is familiar for free fields: the commutator is often supported sharply on $t^2=\mathbf x^2$.

## Time-ordered correlators

The time-ordered two-point function is

$$
G_T(t,\mathbf x)
=
\langle T\mathcal O(t,\mathbf x)\mathcal O(0)\rangle.
$$

In terms of Wightman functions,

$$
G_T(t,\mathbf x)
=
\theta(t)G^>(t,\mathbf x)+\theta(-t)G^<(t,\mathbf x).
$$

For higher-point functions, time ordering is a sum over Wightman orderings weighted by step functions. For example,

$$
\langle T\mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\sum_{\pi\in S_3}
\theta(t_{\pi(1)}>t_{\pi(2)}>t_{\pi(3)})
\langle
\mathcal O_{\pi(1)}\mathcal O_{\pi(2)}\mathcal O_{\pi(3)}
\rangle.
$$

This formula suppresses contact terms at coincident times. In field theory, equal-time contact terms are often essential for Ward identities, anomalies, and conserved charges. In holography they are controlled by boundary counterterms in holographic renormalization.

The main point is that time ordering is not the same as Wightman ordering. Wightman order is an ordering of operators in the product. Time ordering rearranges operators according to real Lorentzian time.

## Commutators and microcausality

The commutator two-point function is

$$
G_{\mathrm{comm}}(x)
=
\langle [\mathcal O(x),\mathcal O(0)]\rangle
=
G^>(x)-G^<(x).
$$

For a local bosonic operator in a unitary relativistic QFT,

$$
[\mathcal O(x),\mathcal O(0)]=0
\qquad
\text{if }x^2>0.
$$

This is microcausality. The Euclidean correlator knows this fact in a somewhat hidden way: spacelike-separated Lorentzian points can be reached without crossing the light-cone branch cut, so the two Wightman orderings agree.

The light cone is the singular surface

$$
x^2=0.
$$

In a CFT, light-cone singularities are especially strong because there is no mass scale to smooth them. This is why Lorentzian CFT is more delicate than Euclidean CFT. The Euclidean OPE is naturally organized by radial distance; the Lorentzian theory is also sensitive to causal separation and null limits.

## Retarded and advanced correlators

The retarded correlator measures causal linear response. With our convention,

$$
G_R(x)
=
-i\theta(t)\langle [\mathcal O(x),\mathcal O(0)]\rangle.
$$

The advanced correlator is

$$
G_A(x)
=
i\theta(-t)\langle [\mathcal O(x),\mathcal O(0)]\rangle.
$$

Thus

$$
G_R(t,\mathbf x)=0
\qquad
\text{for }t<0.
$$

For a local relativistic theory, the commutator also vanishes outside the light cone, so the retarded correlator has support only in the future light cone:

$$
G_R(t,\mathbf x)=0
\qquad
\text{unless }t\geq 0\text{ and }t^2\geq \mathbf x^2.
$$

This is the field-theory version of causal propagation. In AdS/CFT, it is the boundary imprint of causal propagation in the bulk.

The retarded correlator is the object that appears in linear response. If the Hamiltonian is perturbed by a source

$$
\delta H(t)=-\int d^{d-1}\mathbf x\,J(t,\mathbf x)\mathcal O(t,\mathbf x),
$$

then the first-order response is

$$
\delta\langle \mathcal O(x)\rangle
=
\int d^d y\,G_R(x-y)J(y),
$$

up to the convention-dependent sign associated with the definition of the source coupling. The important structural point is fixed: the response at $x$ only depends on sources in the causal past of $x$.

## Momentum space and spectral density

Define the Fourier transform by

$$
G_R(\omega,\mathbf k)
=
\int dt\,d^{d-1}\mathbf x\,
e^{i\omega t-i\mathbf k\cdot\mathbf x}
G_R(t,\mathbf x).
$$

Because $G_R(t,\mathbf x)$ has support only for $t\geq 0$, the function $G_R(\omega,\mathbf k)$ is analytic for

$$
\operatorname{Im}\omega>0,
$$

assuming the usual polynomial boundedness appropriate to a local QFT. This analyticity is one of the most useful real-time constraints.

The spectral density is the Fourier transform of the commutator:

$$
\rho(\omega,\mathbf k)
=
\int d^d x\,
e^{i\omega t-i\mathbf k\cdot\mathbf x}
\langle [\mathcal O(x),\mathcal O(0)]\rangle.
$$

With the retarded convention above,

$$
G_R(\omega,\mathbf k)
=
\int_{-\infty}^{\infty}\frac{d\omega'}{2\pi}
\frac{\rho(\omega',\mathbf k)}{\omega-\omega'+i0}
+\text{contact terms}.
$$

Therefore

$$
\rho(\omega,\mathbf k)=-2\operatorname{Im}G_R(\omega,\mathbf k)
$$

for the nonlocal part of the correlator. Contact terms are real polynomials in momenta and do not contribute to spectral weight, although they do affect local Ward identities.

For a Hermitian bosonic operator,

$$
\rho(-\omega,-\mathbf k)=-\rho(\omega,\mathbf k).
$$

In a unitary vacuum theory, positive energy implies that the Wightman spectral weight has support at positive frequency. For scalar primaries in a CFT, the nonlocal momentum-space two-point function has the schematic form

$$
G_R(\omega,\mathbf k)
\propto
\left[\mathbf k^2-(\omega+i0)^2\right]^{\Delta-d/2},
$$

up to normalization and contact terms. Its branch cut lies where

$$
\omega^2>\mathbf k^2,
$$

namely inside the Lorentzian light cone in momentum space. This is the momentum-space version of causal spectral support.

## Lorentzian cross-ratios and sheets

For four scalar operators, Euclidean conformal symmetry organizes the correlator using cross-ratios. In $d=2$ one often writes

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

In Euclidean signature, $\bar z$ is the complex conjugate of $z$. In Lorentzian signature, $z$ and $\bar z$ should be treated as independent variables after analytic continuation. The same Euclidean function can have many Lorentzian boundary values depending on how the continuation winds around branch points at

$$
z=0,
\qquad
z=1,
\qquad
z=\infty,
$$

and similarly for $\bar z$.

This is not just a technical nuisance. Different sheets correspond to different physical orderings. For example:

- ordinary time-ordered correlators live on one set of sheets;
- commutators are discontinuities across branch cuts;
- out-of-time-ordered correlators live on sheets reached by nontrivial analytic continuation;
- Regge and chaos limits are Lorentzian sheet limits, not ordinary Euclidean limits.

This is why modern CFT, especially the bootstrap relevant for AdS/CFT, treats Lorentzian analyticity as part of the physical structure of the theory.

## Lorentzian OPE: what changes?

The Euclidean OPE is a convergent expansion under radial ordering. Schematically,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0)+\cdots.
$$

In Lorentzian signature, this statement requires more care. The singularity structure depends on whether $x$ is spacelike, timelike, or null.

For spacelike separation, one can often continue from Euclidean signature without crossing singularities. The OPE behaves much like the Euclidean OPE.

For timelike separation, the operator ordering matters. The same formal OPE may land on different analytic sheets.

For null separation,

$$
x^2\to 0,
$$

operators become singular in a particularly strong way. The appropriate expansion is the lightcone OPE, organized not simply by dimension $\Delta$, but by twist

$$
\tau=\Delta-\ell.
$$

Low-twist operators dominate lightcone limits. This fact is one of the main engines behind the lightcone bootstrap, the large-spin expansion, and many CFT derivations of bulk locality constraints in AdS/CFT.

## Thermal and Schwinger-Keldysh correlators

In a thermal state,

$$
\langle \cdots\rangle_\beta
=
\frac{1}{Z(\beta)}\operatorname{Tr}\left(e^{-\beta H}\cdots\right),
$$

real-time correlators obey the KMS condition. For two bosonic operators,

$$
G^>_\beta(t)=G^<_\beta(t+i\beta).
$$

This is the thermal version of Euclidean periodicity in imaginary time.

The most systematic way to organize real-time thermal correlators is the Schwinger-Keldysh contour. Instead of a single time-ordered path integral, one uses a contour with forward and backward Lorentzian segments, and sometimes Euclidean caps. Different placements of operators on the contour produce Wightman, retarded, advanced, time-ordered, anti-time-ordered, and out-of-time-ordered correlators.

This language is indispensable for real-time holography. Black hole horizons naturally impose retarded boundary conditions, while more general Schwinger-Keldysh contours require a corresponding contour prescription in the bulk.

## Contact terms and scheme dependence

Many CFT correlators are only uniquely defined at separated points. When points collide, one may add local contact terms consistent with symmetries. In position space these are derivatives of delta functions. In momentum space they are polynomials in $\omega$ and $\mathbf k$.

For example, a two-point function may have the form

$$
G(\omega,\mathbf k)
=
G_{\mathrm{nonlocal}}(\omega,\mathbf k)
+P(\omega,\mathbf k),
$$

where $P$ is a polynomial. The nonlocal part determines spectral cuts and long-distance physics. The polynomial part is a choice of local counterterms.

In AdS/CFT, this distinction is not optional. Holographic correlators are computed by varying an on-shell bulk action. That action diverges near the AdS boundary and must be renormalized by adding local boundary counterterms. These counterterms precisely produce contact-term ambiguities in CFT correlators.

## AdS/CFT checkpoint

Lorentzian correlators are where the CFT starts sounding like bulk spacetime.

The Euclidean dictionary says roughly

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\phi_{\partial}=J].
$$

The Lorentzian dictionary asks a sharper question: which bulk solution computes which CFT correlator?

For the retarded correlator at finite temperature, the answer is especially important:

$$
G_R(\omega,\mathbf k)
\quad\longleftrightarrow\quad
\text{bulk solution with infalling boundary condition at the horizon}.
$$

The physics is transparent. A retarded response is causal: the system absorbs disturbances after the source is applied. A black hole horizon also absorbs. Infalling boundary conditions implement this causal absorption in the bulk.

Several central holographic ideas are already visible from the CFT side:

- Poles of $G_R(\omega,\mathbf k)$ are normal modes in global AdS or quasinormal modes in black hole backgrounds.
- Branch cuts in $G_R$ indicate continua of states or large-$N$ limits of dense spectra.
- Spectral density measures how strongly the CFT absorbs energy at given $(\omega,\mathbf k)$.
- The vanishing of commutators at spacelike separation is the boundary version of causal propagation.
- Lorentzian four-point functions diagnose bulk scattering, shock waves, chaos, and constraints from causality.

This is why a holographer cannot stop at Euclidean correlators. Euclidean CFT data is the compact encoding of the theory; Lorentzian correlators reveal its causal dynamics.

## Common pitfalls

The first common pitfall is to write

$$
\frac{1}{(-t^2+\mathbf x^2)^\Delta}
$$

without an $i\epsilon$ prescription. For non-integer $\Delta$, this expression is not a distribution until a branch prescription is specified.

The second common pitfall is to confuse Wightman ordering with time ordering. The correlator

$$
\langle \mathcal O_1(t_1)\mathcal O_2(t_2)\rangle
$$

has the operator order shown, even if $t_2>t_1$. A time-ordered correlator would rearrange the operators.

The third common pitfall is to ignore contact terms. Contact terms do not matter at separated points, but they matter for Ward identities, anomalies, charge commutators, and holographic renormalization.

The fourth common pitfall is to assume that a Euclidean cross-ratio limit has the same meaning in Lorentzian signature. In Lorentzian CFT, the sheet matters. Going around a branch point changes the physical correlator.

## Summary

Euclidean CFT correlators are the starting point, but Lorentzian CFT requires analytic continuation with a specified $i\epsilon$ prescription. Wightman functions are boundary values with a chosen operator ordering. Time-ordered correlators are step-function combinations of Wightman functions. Commutators are discontinuities across Lorentzian branch cuts. Retarded correlators encode causal response and have analytic structure in the upper half of the complex frequency plane.

For AdS/CFT, these ideas are not decorative. They are the boundary formulation of bulk causality, horizon absorption, quasinormal modes, real-time response, and eventually bulk scattering.

## Exercises

### Exercise 1. Derive the Wightman $i\epsilon$ prescription

Start from the Euclidean scalar two-point function

$$
G_E(\tau,\mathbf x)=\frac{C_{\mathcal O}}{(\tau^2+\mathbf x^2)^\Delta}.
$$

Use $\tau=\epsilon+i t$ with $\epsilon>0$ to derive

$$
G^>(t,\mathbf x)
=
\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t-i0)^2\right]^\Delta}.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute

$$
\tau=\epsilon+i t.
$$

Then

$$
\tau^2+\mathbf x^2
=
(\epsilon+i t)^2+\mathbf x^2
=
\epsilon^2-t^2+2i\epsilon t+\mathbf x^2.
$$

But

$$
-(t-i\epsilon)^2+\mathbf x^2
=
-t^2+2i\epsilon t+\epsilon^2+\mathbf x^2.
$$

Therefore

$$
\tau^2+\mathbf x^2
=
\mathbf x^2-(t-i\epsilon)^2.
$$

Taking $\epsilon\to0^+$ gives

$$
G^>(t,\mathbf x)
=
\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t-i0)^2\right]^\Delta}.
$$

The sign of $i0$ came from the fact that the first operator has the larger Euclidean regulator.

</details>

### Exercise 2. Show that the scalar commutator vanishes at spacelike separation

Using

$$
G^>(t,\mathbf x)=\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t-i0)^2\right]^\Delta},
\qquad
G^<(t,\mathbf x)=\frac{C_{\mathcal O}}{\left[\mathbf x^2-(t+i0)^2\right]^\Delta},
$$

show that $G^>(t,\mathbf x)-G^<(t,\mathbf x)=0$ when $\mathbf x^2-t^2>0$.

<details>
<summary><strong>Solution</strong></summary>

For spacelike separation,

$$
\mathbf x^2-t^2>0.
$$

The real part of the denominator is positive. Taking $\epsilon\to0^+$,

$$
\mathbf x^2-(t\mp i\epsilon)^2
=
\mathbf x^2-t^2\pm 2i\epsilon t+\epsilon^2.
$$

Both prescriptions approach the same positive real number. No branch cut is crossed. Therefore

$$
\left[\mathbf x^2-(t-i0)^2\right]^{-\Delta}
=
\left[\mathbf x^2-(t+i0)^2\right]^{-\Delta},
$$

and hence

$$
G^>(t,\mathbf x)-G^<(t,\mathbf x)=0.
$$

This is the two-point manifestation of microcausality.

</details>

### Exercise 3. Retarded analyticity

Let

$$
G_R(\omega,\mathbf k)
=
\int dt\,d^{d-1}\mathbf x\,
e^{i\omega t-i\mathbf k\cdot\mathbf x}G_R(t,\mathbf x),
$$

with $G_R(t,\mathbf x)=0$ for $t<0$. Explain why $G_R(\omega,\mathbf k)$ is analytic for $\operatorname{Im}\omega>0$, assuming suitable boundedness at large $t$.

<details>
<summary><strong>Solution</strong></summary>

Because $G_R(t,\mathbf x)$ vanishes for $t<0$, the time integral is

$$
\int_0^\infty dt\,e^{i\omega t}G_R(t,\mathbf k).
$$

Write

$$
\omega=\omega_R+i\omega_I.
$$

Then

$$
e^{i\omega t}=e^{i\omega_R t}e^{-\omega_I t}.
$$

For $\omega_I>0$, the factor $e^{-\omega_I t}$ damps the large-$t$ integral. Under the standard assumptions that the real-time distribution is sufficiently well behaved after smearing, the integral defines an analytic function of $\omega$ in the upper half-plane.

The physical content is simple: causality in time implies analyticity in frequency.

</details>

### Exercise 4. Choose the regulators for a Wightman ordering

What $\epsilon$ ordering computes the Lorentzian Wightman correlator

$$
\langle \mathcal O_2(t_2)\mathcal O_1(t_1)\mathcal O_3(t_3)\rangle?
$$

<details>
<summary><strong>Solution</strong></summary>

The $\epsilon$ ordering follows the operator ordering, not the real-time ordering. Therefore one should take

$$
\epsilon_2>\epsilon_1>\epsilon_3>0.
$$

Then continue the Euclidean correlator by

$$
\tau_i=\epsilon_i+i t_i.
$$

The real values of $t_1,t_2,t_3$ may be in any order. The Wightman product remains

$$
\mathcal O_2\mathcal O_1\mathcal O_3.
$$

</details>

### Exercise 5. Retarded response from Wightman functions

Show that the retarded correlator can be written as

$$
G_R(t,\mathbf x)
=
-i\theta(t)\left(G^>(t,\mathbf x)-G^<(t,\mathbf x)\right).
$$

Why does this vanish for $t<0$?

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
G_R(t,\mathbf x)
=
-i\theta(t)\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle.
$$

The commutator expectation value is

$$
\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle
=
\langle\mathcal O(t,\mathbf x)\mathcal O(0)\rangle
-
\langle\mathcal O(0)\mathcal O(t,\mathbf x)\rangle.
$$

Thus

$$
\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle
=
G^>(t,\mathbf x)-G^<(t,\mathbf x),
$$

and so

$$
G_R(t,\mathbf x)
=
-i\theta(t)\left(G^>(t,\mathbf x)-G^<(t,\mathbf x)\right).
$$

It vanishes for $t<0$ because $\theta(t)=0$ there. This is the defining causal property of retarded response.

</details>

## Further reading

For the QFT foundations, review analytic continuation, Wightman functions, spectral representations, and the Källén-Lehmann representation in a standard quantum field theory text. For CFT applications, study Lorentzian four-point functions, lightcone OPE limits, reflection positivity, and the Lorentzian inversion formula. For AdS/CFT, the essential next step is the real-time prescription for holographic retarded correlators and the relation between retarded poles and quasinormal modes.
