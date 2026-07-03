---
title: "Analyticity and Causality"
description: "How microcausality, spectral support, unitarity, and boundary conditions produce analytic propagators, dispersion relations, poles, cuts, and causality constraints."
sidebar:
  label: "Analyticity and Causality"
  order: 6
---

## Summary

In QFT, **analyticity** is not a decorative complex-analysis trick. It is the momentum-space shadow of causality, positive energy, and locality.

The basic slogan is:

$$
\boxed{\text{causal support in spacetime}\quad\Longrightarrow\quad\text{analyticity in complex momentum space}.}
$$

A retarded response function is the cleanest example. If

$$
G_R(t,\mathbf x)=0\qquad (t<0),
$$

then its frequency-space transform

$$
\widetilde G_R(\omega,\mathbf p)
=\int_{-\infty}^{\infty}dt\,d^3x\,
 e^{i\omega t-i\mathbf p\cdot\mathbf x}G_R(t,\mathbf x)
$$

is analytic for

$$
\operatorname{Im}\omega>0,
$$

because the factor $e^{i\omega t}=e^{i(\operatorname{Re}\omega)t-(\operatorname{Im}\omega)t}$ damps the integral at positive time. Similarly, advanced functions are analytic in the lower half-plane. In a relativistic theory, microcausality sharpens the statement: commutators vanish at spacelike separation, so retarded commutators have support only in the future light cone, not merely at positive time.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Causality, analytic domains, discontinuities, and dispersion relations](/figures/foundations/analyticity-causality-map.svg)

<figcaption>

Causal support makes Fourier transforms analytic in appropriate half-planes or tube domains. Boundary values on the real axis differ by discontinuities; unitarity and spectral positivity identify those discontinuities with physical intermediate states. Dispersion relations then reconstruct analytic functions from their discontinuities, up to subtraction polynomials.

</figcaption>
</figure>

This page gives the structural version of a story that already appeared in pieces: the retarded and advanced propagators have pole prescriptions fixed by causal support; the Feynman propagator has a different boundary condition fixed by the vacuum; the Källén–Lehmann representation turns Hilbert-space positivity into an analytic two-point function with poles and cuts; and unitarity turns discontinuities of scattering amplitudes into sums over physical intermediate states. Weinberg's dispersion-relation discussion is the canonical reference for the bridge from microscopic causality to analyticity of scattering amplitudes: the modern derivation uses the vanishing of commutators outside the light cone, not merely an optical-medium analogy (Weinberg 1995, Vol. I, §10.8). Coleman and Srednicki develop the neighboring pieces through LSZ, spectral representations, and perturbative amplitudes.

## Prerequisites

You should know [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/), [Spectral Condition](/foundations/structural-principles/spectral-condition/), [Unitarity](/foundations/structural-principles/unitarity/), [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/), [i-Epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/).

:::note[Conventions]
We use qft.org's mostly-minus metric,

$$
p^2=(p^0)^2-\mathbf p^2,
$$

and Fourier convention

$$
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x).
$$

For fixed spatial momentum, the frequency transform therefore contains $e^{i\omega t}$. With this convention, a retarded function supported at $t\ge0$ is analytic for $\operatorname{Im}\omega>0$, and an advanced function supported at $t\le0$ is analytic for $\operatorname{Im}\omega<0$.
:::

:::note[Assumptions]
The clean structural statements below assume a flat-spacetime relativistic QFT with a stable Poincaré-invariant vacuum, positive-energy spectrum, local fields or local gauge-invariant operators, and a positive physical Hilbert space. Scattering-amplitude analyticity also assumes appropriate asymptotic states and polynomial boundedness conditions. Gauge-fixed fields, massless particles, confinement, thermal states, finite density, curved spacetime, and long-range forces can require refined versions.
:::

## What analyticity means here

A function of a complex variable is analytic if it is complex differentiable in an open domain. In QFT the relevant variables are usually complexified versions of real physical variables:

$$
\omega\in\mathbb C,
\qquad
p^0\in\mathbb C,
\qquad
p^2\in\mathbb C,
\qquad
s,t,u\in\mathbb C.
$$

Physical measurements live on the real boundary. Analyticity says that the physical function is the boundary value of a holomorphic function in some larger complex domain.

This matters because a holomorphic function is rigid. If we know its singularities, discontinuities, asymptotic behavior, and a finite number of subtraction constants, we can often reconstruct it. That is the logic behind dispersion relations, Kramers–Kronig relations, spectral representations, sum rules, positivity bounds, crossing constraints, and many bootstrap arguments.

The important point for Foundations is not that every amplitude is magically analytic everywhere. It is that **the locations and meanings of nonanalyticities are physical**.

| Nonanalytic feature | Physical meaning |
|---|---|
| isolated pole | stable one-particle state or bound state |
| pole shifted off the real axis | unstable resonance, after appropriate continuation |
| branch cut | multiparticle threshold or continuum of states |
| discontinuity across a cut | spectral density or absorptive part |
| subtraction polynomial | local/contact ambiguity or UV information |
| failure of expected analyticity | possible failure of locality, causality, positivity, or assumptions |

Analyticity turns invisible structural assumptions into visible complex-plane geometry.

## The prototype: retarded functions

Let $A(t,\mathbf x)$ and $B(0)$ be local bosonic operators. Define the retarded correlator

$$
G_R(t,\mathbf x)
=i\theta(t)\langle\Omega|[A(t,\mathbf x),B(0)]|\Omega\rangle.
$$

For fermionic operators one uses the appropriate graded commutator. The precise sign convention is less important than the support property:

$$
G_R(t,\mathbf x)=0\qquad(t<0).
$$

At fixed spatial momentum,

$$
\widetilde G_R(\omega,\mathbf p)
=\int_{0}^{\infty}dt\,e^{i\omega t}
\int d^3x\,e^{-i\mathbf p\cdot\mathbf x}
 i\langle\Omega|[A(t,\mathbf x),B(0)]|\Omega\rangle.
$$

If $\operatorname{Im}\omega>0$, then

$$
e^{i\omega t}=e^{i(\operatorname{Re}\omega)t}e^{-(\operatorname{Im}\omega)t}
$$

provides exponential damping at large positive time. For ordinary functions this makes analyticity immediate. For distributions, the same idea is made precise by interpreting $\widetilde G_R$ as an analytic function whose boundary value on the real axis is the physical retarded distribution.

The advanced function

$$
G_A(t,\mathbf x)=-i\theta(-t)\langle\Omega|[A(t,\mathbf x),B(0)]|\Omega\rangle
$$

has support at $t\le0$, so its transform is analytic for $\operatorname{Im}\omega<0$.

The free scalar retarded propagator makes this familiar. In qft.org conventions,

$$
\widetilde G_R(p)=
-\frac{1}{(p^0+i\epsilon)^2-E_{\mathbf p}^2},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Both poles lie below the real $p^0$ axis:

$$
p^0=\pm E_{\mathbf p}-i\epsilon.
$$

So $\widetilde G_R$ is analytic in the upper half-plane. The advanced propagator has both poles above the real axis and is analytic in the lower half-plane.

This is the simplest version of a huge theme: **support restrictions in one domain become analyticity restrictions in the Fourier-dual domain**.

## Microcausality strengthens the support

The retarded condition $G_R(t,\mathbf x)=0$ for $t<0$ is causal in a preferred time coordinate. Relativistic locality says more. If $A$ and $B$ are local bosonic observables, then

$$
[A(x),B(0)]=0\qquad(x^2<0).
$$

For fermionic fields the graded version is used. Therefore the retarded commutator has support only in or on the **future light cone**:

$$
G_R(x)=0
\qquad\text{unless}\qquad
x^0\ge0,
\quad x^2\ge0.
$$

This light-cone support leads to analyticity in relativistic **tube domains**, not just ordinary upper and lower half-planes. Roughly, if the imaginary part of the complexified momentum lies in the dual forward cone, the Fourier transform receives exponential damping on the future cone. The full theorem-level story belongs in rigorous QFT, but the physical content is exactly the same as the one-dimensional retarded example.

Microcausality is also what makes the analytic continuation compatible with Lorentz invariance. A merely time-retarded function in a nonrelativistic theory can be analytic in frequency. A relativistic local theory additionally knows about spacelike separation, light cones, and invariant thresholds.

## Boundary values and discontinuities

A physical correlator often appears as the boundary value of an analytic function from one side of a cut. Let $F(z)$ be analytic away from a cut along part of the real axis. The two boundary values are

$$
F_+(x)=\lim_{\epsilon\downarrow0}F(x+i\epsilon),
\qquad
F_-(x)=\lim_{\epsilon\downarrow0}F(x-i\epsilon).
$$

The discontinuity is

$$
\operatorname{Disc}F(x)=F_+(x)-F_-(x).
$$

When $F_-(x)=F_+(x)^*$, as happens in many real analyticity situations, this becomes

$$
\operatorname{Disc}F(x)=2i\operatorname{Im}F_+(x).
$$

In QFT, the discontinuity is rarely just a formal complex-analysis object. It usually has a Hilbert-space interpretation. For a two-point function, it is the spectral density. For a scattering amplitude, it is the absorptive part. For a loop integral, it is produced by putting intermediate lines on shell. Unitarity tells us that these discontinuities are built from physical intermediate states.

That is why analyticity and unitarity work so well together: analyticity says where the function can be reconstructed from its boundary data; unitarity gives the boundary data a positive physical meaning.

## Dispersion relations

Suppose $F(z)$ is analytic in the complex $z$ plane except for a cut on the real axis beginning at $s_0$, and suppose $F(z)$ falls sufficiently fast at infinity. Then Cauchy's theorem gives the unsubtracted dispersion relation

$$
F(z)=\frac{1}{2\pi i}\int_{s_0}^{\infty}ds\,
\frac{\operatorname{Disc}F(s)}{s-z}.
$$

If $F_-(s)=F_+(s)^*$, this is

$$
F(z)=\frac{1}{\pi}\int_{s_0}^{\infty}ds\,
\frac{\operatorname{Im}F(s+i0)}{s-z}.
$$

Most QFT functions do not fall fast enough for this to be literally true without modifications. If $F(z)$ grows at infinity, one performs **subtractions**. A common $N$-subtracted form around $z=z_0$ is

$$
F(z)=P_{N-1}(z)
+\frac{(z-z_0)^N}{\pi}
\int_{s_0}^{\infty}ds\,
\frac{\operatorname{Im}F(s+i0)}{(s-z_0)^N(s-z)}.
$$

Here $P_{N-1}$ is a polynomial of degree at most $N-1$. Physically, these subtraction constants encode local information not fixed by the absorptive part alone. In an EFT, they are cousins of local Wilson coefficients. In a renormalized QFT, they are tied to renormalization conditions.

So a dispersion relation says:

$$
\boxed{\text{analyticity} + \text{asymptotic control}
\quad\Longrightarrow\quad
\text{real part from discontinuity plus local data}.}
$$

This is the precise sense in which causality can constrain real parts of amplitudes through imaginary parts.

## The two-point case

The Källén–Lehmann representation is the simplest exact QFT dispersion relation. For a scalar local operator with the right quantum numbers, the Feynman two-point function has the schematic form

$$
\Delta_F(p^2)=
\int_0^\infty d\mu^2\,\rho(\mu^2)
\frac{i}{p^2-\mu^2+i\epsilon},
$$

with

$$
\rho(\mu^2)\ge0
$$

for a positive-norm Hilbert space. The integration variable $\mu^2$ is the invariant mass squared of intermediate states.

A stable one-particle state contributes a delta function,

$$
\rho(\mu^2)\supset Z\delta(\mu^2-m^2),
$$

so the propagator has an isolated pole at $p^2=m^2$. Multiparticle states contribute continua, so the propagator has branch cuts beginning at thresholds such as

$$
p^2=(m_1+m_2)^2.
$$

This representation packages several structural principles at once.

| Principle | Role in the two-point function |
|---|---|
| spectral condition | intermediate states have $p^0\ge0$ and $p^2\ge0$ |
| Hilbert-space positivity | $\rho(\mu^2)\ge0$ |
| locality | boundary values satisfy causal commutator relations |
| analyticity | poles and cuts appear in the complex $p^2$ plane |
| unitarity | discontinuities count physical intermediate states |

This is why the spectral representation is more than a formula for propagators. It is a diagnostic for whether a proposed two-point function can belong to an ordinary unitary Lorentzian QFT.

## The Feynman prescription is different

The Feynman propagator is analytic in a different pattern from the retarded propagator. For the free scalar,

$$
\widetilde\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}
=\frac{i}{(p^0)^2-E_{\mathbf p}^2+i\epsilon}.
$$

The positive-energy pole lies below the real $p^0$ axis, while the negative-energy pole lies above it:

$$
p^0=+E_{\mathbf p}-i\epsilon,
\qquad
p^0=-E_{\mathbf p}+i\epsilon.
$$

This is not the pole pattern of a causal response function. It is the pole pattern of a **vacuum time-ordered** correlator. It tells positive-frequency modes to propagate forward in time and negative-frequency modes backward in time. That is the correct Green function for perturbative scattering and path integrals, but it is not the same object as the retarded response.

This distinction prevents a common confusion:

$$
\boxed{\text{Feynman propagation is not the same as causal signal propagation}.}
$$

The Feynman propagator can be nonzero at spacelike separation. That does not violate causality because causal influence is governed by commutators and retarded functions. Microcausality requires the commutator to vanish outside the light cone, not the time-ordered two-point function.

## Scattering amplitudes

Analyticity of scattering amplitudes is deeper and more delicate than analyticity of two-point functions, but the guiding principles are the same.

A scattering amplitude is obtained from time-ordered correlators by LSZ reduction. The time-ordered correlator has singularities when intermediate states can go on shell. LSZ strips external propagators and leaves an amplitude whose analytic structure reflects possible physical intermediate channels.

For a two-to-two amplitude, one introduces Mandelstam variables

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

where this page writes the third variable as $\nu$ to avoid conflict with time $t$ in the prose. Many texts write it as $u$.

A pole in the $s$ channel indicates a one-particle intermediate state with invariant mass squared $s=m^2$. A branch cut in the $s$ channel begins when a multiparticle intermediate state can be produced. The discontinuity across that cut is constrained by unitarity:

$$
\operatorname{Disc}_s\mathcal M
\sim
\sum_X \mathcal M_{\text{left}\to X}\,
\mathcal M_{\text{right}\to X}^*,
$$

where the sum/integral runs over on-shell intermediate states allowed by the quantum numbers and phase space.

Crossing symmetry relates different physical regions of the same analytic function. An amplitude for $a+b\to c+d$ can be analytically continued to an amplitude involving antiparticles, such as $a+\bar c\to\bar b+d$, after continuing through the appropriate complex kinematic domain. The deep theorem-level conditions behind crossing are subtle, but the physical idea is already visible in perturbation theory: the same Feynman graph can represent different processes depending on which external legs are viewed as incoming or outgoing.

## Forward amplitudes and the optical theorem

Forward scattering is the most accessible place where analyticity and unitarity meet. Let $F(\omega)$ denote a forward amplitude as a function of projectile energy in the target rest frame. Under suitable assumptions, microscopic causality implies that $F(\omega)$ is analytic in the complex $\omega$ plane cut along physical real-energy regions. Weinberg's derivation rewrites time-ordered products in terms of commutators; because microscopic causality makes those commutators vanish outside the light cone, retarded and advanced pieces are analytic in opposite half-planes (Weinberg 1995, Vol. I, §10.8).

The optical theorem gives

$$
\operatorname{Im}F(\omega+i0)
\propto
\omega\,\sigma_{\rm tot}(\omega),
$$

up to conventional normalization factors. A dispersion relation then expresses the real part of $F$ in terms of an integral over total cross sections, plus possible subtraction constants.

That chain is worth spelling out:

$$
\boxed{
\text{microcausality}
\Rightarrow
\text{analyticity}
\Rightarrow
\text{dispersion relation}
\xleftarrow{\text{unitarity}}
\text{total cross sections}.
}
$$

This is one of the great structural bridges in QFT. It says that a real part of an amplitude, which may look like a virtual off-shell effect, is constrained by measurable on-shell absorption probabilities.

## Contact terms and subtraction polynomials

Time-ordered products contain step functions. When differential operators act on them, derivatives of step functions produce **contact terms** supported at coincident points. In momentum space, contact terms become polynomials.

For example, differentiating a time-ordered product can produce terms proportional to

$$
\delta^{(4)}(x-y)
$$

and its derivatives. Their Fourier transforms are polynomial in the external momenta. Such terms do not produce cuts. They affect local pieces, Ward identities, and subtraction constants.

This is why dispersion relations usually reconstruct a function only up to polynomial data. The discontinuity sees long-distance propagation of intermediate states. It does not see arbitrary local contact terms unless additional renormalization conditions or symmetry constraints are supplied.

In EFT language, the cut part is associated with propagation over finite distances and on-shell intermediate states; the polynomial part is associated with local operators.

## Wick rotation and analyticity

Wick rotation is also an analyticity statement. A formal replacement

$$
t=-i\tau
$$

is justified only when the integration contour in complex energy can be rotated without crossing singularities and when the arcs at infinity do not contribute. The $i\epsilon$ prescription tells us where the poles sit, so it tells us how to rotate.

For a free scalar loop integral, the Feynman prescription puts poles so that the $p^0$ contour can be deformed to the imaginary axis in a controlled way. In interacting theories, thresholds and branch cuts make the contour story more elaborate. In thermal field theory, finite density, real-time nonequilibrium physics, or curved spacetime, the relation between Euclidean and Lorentzian correlators can become substantially more delicate.

So the safe slogan is:

$$
\boxed{\text{Euclidean continuation requires analytic control, not just replacing symbols}.}
$$

This is why [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) and [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) belong next to analyticity in the Foundations map.

## Positivity bounds preview

Analyticity becomes especially powerful when combined with unitarity, crossing, and polynomial boundedness. A typical modern use is a **positivity bound**. The rough idea is:

1. write a subtracted dispersion relation for a low-energy amplitude;
2. use unitarity to make the discontinuity a positive sum over physical states;
3. infer positivity constraints on low-energy Taylor coefficients.

In an EFT, those Taylor coefficients are Wilson coefficients. Therefore general principles of UV-completable QFT can constrain the signs of low-energy interactions.

The full subject belongs in EFT, amplitudes, and bootstrap sections. Foundations only needs the moral: analyticity turns causality into calculational constraints, and unitarity turns discontinuities into positive data.

## What can fail

Analyticity statements are powerful because their hypotheses are strong. Here are common failure modes or caveats.

### Long-range forces

Massless particles can create infrared subtleties. In QED, charged asymptotic states are not ordinary Fock states because they are accompanied by soft photon clouds. Some naive S-matrix analyticity statements must be modified.

### Confinement

In a confining theory, quark and gluon fields are not associated with asymptotic colored particles. Gauge-invariant correlators can have healthy analytic structure, but colored gauge-fixed Green functions are not physical observables.

### Gauge fixing

Gauge-fixed formulations may contain ghosts, longitudinal modes, or negative-norm states. Analyticity and unitarity should be interpreted in the physical Hilbert space, or in BRST cohomology, not necessarily for every component of every gauge-fixed propagator.

### Unstable particles

An unstable particle does not produce a stable one-particle pole on the physical real sheet. Resonances appear as poles on analytically continued unphysical sheets. This is one reason analytic continuation is not optional ornamentation in scattering theory; it is how resonances are defined precisely.

### Thermal and finite-density systems

At finite temperature, Lorentz invariance is broken by the thermal rest frame. Retarded correlators are still analytic in the upper half-frequency plane, but spectral representations, KMS relations, Matsubara frequencies, and real-time analytic continuation require their own framework.

### Curved spacetime

Without global time translations, there may be no global conserved energy and no ordinary momentum-space analyticity. Local causality still matters, but the analytic machinery changes.

## Common pitfalls

### Pitfall 1: Thinking every nonzero spacelike propagator violates causality

The Feynman propagator need not vanish at spacelike separation. Causality is encoded in commutators and retarded response functions. The vanishing statement is

$$
[A(x),B(y)]=0\qquad((x-y)^2<0),
$$

for local observables, not

$$
\langle0|T A(x)B(y)|0\rangle=0.
$$

### Pitfall 2: Treating the epsilon prescription as arbitrary decoration

The $i\epsilon$ prescription is boundary-condition data. It tells us which analytic boundary value is meant and which contour is allowed. Changing it changes the Green function.

### Pitfall 3: Forgetting subtraction constants

A discontinuity alone does not always determine the whole function. Polynomial terms have no discontinuity across the cut. They must be fixed by renormalization conditions, low-energy data, symmetry, or asymptotic assumptions.

### Pitfall 4: Confusing Euclidean regularity with Lorentzian unitarity

A Euclidean correlator can look perfectly smooth while failing reflection positivity. A Lorentzian analytic continuation is physically acceptable only when it reconstructs a positive Hilbert space with causal dynamics.

### Pitfall 5: Overstating scattering analyticity

The analytic structure of full scattering amplitudes is subtle, especially with massless particles, gauge theories, bound states, and multiple variables. The foundational principle is robust; the theorem-level domain depends on hypotheses.

## Relations to other pages

- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) supplies the spacelike-commutator condition behind the analytic support argument.
- [Spectral Condition](/foundations/structural-principles/spectral-condition/) supplies positive-energy support, which gives Wightman functions and spectral densities their one-sided structure.
- [Unitarity](/foundations/structural-principles/unitarity/) explains why discontinuities of amplitudes are sums over physical intermediate states.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) is the exact two-point example of analyticity, positivity, poles, and cuts.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) gives the pole prescriptions and causal support of response functions.
- [i-Epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) explains how pole placement selects boundary conditions.
- [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) explains the Euclidean positivity condition needed to reconstruct Lorentzian unitarity.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explains how time-ordered correlators become scattering amplitudes.

## Exercises

### Exercise 1: Retarded analyticity in the upper half-plane

Let $R(t)$ be a tempered function with $R(t)=0$ for $t<0$ and assume it does not grow exponentially at $t\to+\infty$. Define

$$
\widetilde R(\omega)=\int_{0}^{\infty}dt\,e^{i\omega t}R(t).
$$

Show why $\widetilde R(\omega)$ is analytic for $\operatorname{Im}\omega>0$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\omega=a+ib,
\qquad b>0.
$$

Then

$$
e^{i\omega t}=e^{iat}e^{-bt}.
$$

The factor $e^{-bt}$ damps the integral at large positive $t$. Differentiating with respect to $\omega$ brings down factors of $it$:

$$
\frac{d^n\widetilde R}{d\omega^n}
=\int_0^\infty dt\,(it)^n e^{i\omega t}R(t),
$$

and the same exponential damping controls these integrals in compact subsets of the upper half-plane. Thus $\widetilde R$ is analytic there. For distributions this argument is interpreted in the standard boundary-value sense.

</details>

### Exercise 2: Advanced analyticity

Let

$$
A(t)=0\qquad(t>0)
$$

and define

$$
\widetilde A(\omega)=\int_{-\infty}^{0}dt\,e^{i\omega t}A(t).
$$

Which half-plane is the analytic domain?

<details>
<summary><strong>Solution</strong></summary>

Again write $\omega=a+ib$. For $t<0$,

$$
e^{i\omega t}=e^{iat}e^{-bt}.
$$

Since $t<0$, the factor $e^{-bt}$ damps the integral at $t\to-\infty$ only when $b<0$. Therefore $\widetilde A(\omega)$ is analytic for

$$
\operatorname{Im}\omega<0.
$$

This is the advanced analogue of retarded analyticity.

</details>

### Exercise 3: Pole placement for the free retarded propagator

For the free scalar retarded propagator,

$$
\widetilde G_R(p)=
-\frac{1}{(p^0+i\epsilon)^2-E_{\mathbf p}^2},
$$

find the pole locations and explain the support property.

<details>
<summary><strong>Solution</strong></summary>

The denominator vanishes when

$$
(p^0+i\epsilon)^2=E_{\mathbf p}^2,
$$

so

$$
p^0=+E_{\mathbf p}-i\epsilon,
\qquad
p^0=-E_{\mathbf p}-i\epsilon.
$$

Both poles lie below the real $p^0$ axis. In the inverse transform, for $t<0$ one closes the contour in the upper half-plane, where there are no poles. Therefore the integral vanishes for $t<0$. This is the retarded boundary condition.

</details>

### Exercise 4: A one-cut dispersion relation

Assume $F(z)$ is analytic in the complex $z$ plane except for a cut $[s_0,\infty)$ and that $F(z)\to0$ fast enough at infinity. Show that

$$
F(z)=\frac{1}{2\pi i}\int_{s_0}^\infty ds\,
\frac{\operatorname{Disc}F(s)}{s-z}.
$$

<details>
<summary><strong>Solution</strong></summary>

Apply Cauchy's formula to a contour enclosing $z$ and wrapping around the cut. Since $F$ vanishes sufficiently fast at infinity, the large-circle contribution vanishes. The contour just above the cut contributes

$$
\int_{s_0}^\infty ds\,\frac{F(s+i0)}{s-z},
$$

while the contour just below the cut runs in the opposite direction and contributes

$$
-\int_{s_0}^\infty ds\,\frac{F(s-i0)}{s-z}.
$$

Thus

$$
F(z)=\frac{1}{2\pi i}\int_{s_0}^\infty ds\,
\frac{F(s+i0)-F(s-i0)}{s-z}
=\frac{1}{2\pi i}\int_{s_0}^\infty ds\,
\frac{\operatorname{Disc}F(s)}{s-z}.
$$

</details>

### Exercise 5: Why contact terms do not create cuts

Suppose a position-space contribution is a derivative of a delta function,

$$
C(x)=c^{\mu_1\cdots\mu_n}\partial_{\mu_1}\cdots\partial_{\mu_n}\delta^{(4)}(x).
$$

Show that its Fourier transform is polynomial in momentum. Why does this not create a branch cut?

<details>
<summary><strong>Solution</strong></summary>

Using qft.org's transform convention,

$$
\widetilde C(p)=\int d^4x\,e^{ip\cdot x}C(x).
$$

Integrating by parts gives

$$
\widetilde C(p)
=c^{\mu_1\cdots\mu_n}(-ip_{\mu_1})\cdots(-ip_{\mu_n}).
$$

This is a polynomial in $p$. Polynomials are entire functions: they are analytic everywhere in the finite complex plane and have no branch cuts. Therefore contact terms can affect subtraction polynomials but not discontinuities across physical cuts.

</details>

### Exercise 6: Spectral density and positivity

Consider the scalar spectral representation

$$
\Delta_F(p^2)=\int_0^\infty d\mu^2\,\rho(\mu^2)
\frac{i}{p^2-\mu^2+i\epsilon}.
$$

Explain why a negative spectral density would signal trouble in an ordinary unitary QFT.

<details>
<summary><strong>Solution</strong></summary>

The spectral density comes from inserting a complete set of physical intermediate states into a two-point function. Schematically,

$$
\rho(\mu^2)
\sim
\sum_n |\langle n|\mathcal O(0)|0\rangle|^2
\delta(\mu^2-p_n^2),
$$

up to normalization and quantum-number projections. In a positive-norm Hilbert space, each squared matrix element is nonnegative. Therefore

$$
\rho(\mu^2)\ge0.
$$

A negative spectral density would mean either the object is not a physical gauge-invariant correlator, the Hilbert space has negative-norm states, reflection positivity fails in the Euclidean version, or some assumption of ordinary unitary QFT has been abandoned.

</details>

## Sources and further reading

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§10.7–10.8, for the Källén–Lehmann representation, causality relations, analytic properties, and dispersion relations.
- S. Coleman, *Lectures on Quantum Field Theory*, especially the LSZ, scattering, optical-theorem, spectral-representation, and current-algebra discussions.
- M. Srednicki, *Quantum Field Theory*, §§5, 13, and 25, for LSZ, the Lehmann–Källén form of the exact propagator, and the analytic/renormalized propagator viewpoint.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for a classic theorem-level treatment of scattering analyticity.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for Wightman functions, tube domains, and axiomatic locality.
- N. N. Bogoliubov, A. A. Logunov, A. I. Oksak, and I. T. Todorov, *General Principles of Quantum Field Theory*, for a mathematically careful treatment of causality and analyticity.
- Modern EFT and amplitudes references for positivity bounds, dispersion relations, and analyticity constraints in low-energy effective theories.

## Version history

- **2026-05-24:** Initial qft.org page on causal support, half-plane analyticity, microcausality, discontinuities, dispersion relations, spectral representations, scattering analyticity, Wick rotation, and positivity-bound previews.
