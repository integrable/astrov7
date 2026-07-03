---
title: "UV Divergences Preview"
description: "A first encounter with ultraviolet divergences in loop integrals: cutoff dependence, regularization, counterterms, power counting, and the bridge from perturbation theory to renormalization and EFT."
sidebar:
  label: "UV Divergences Preview"
  order: 9
---

## Summary

Loop diagrams integrate over virtual momenta. In an interacting QFT, this means that a low-energy correlator can contain integrals over arbitrarily large internal momentum:

$$
\boxed{
\int\frac{d^4k}{(2\pi)^4}\,F(k,p_i).
}
$$

When the large-$k$ part of the integral does not converge, the diagram has an **ultraviolet divergence**. “Ultraviolet” means high momentum, equivalently short distance. The first lesson is not that QFT has failed. The first lesson is that the parameters appearing in a local Lagrangian are not automatically the measured parameters of the theory.

Regularization makes the problem well-defined by introducing an auxiliary UV scale, for example a momentum cutoff $\Lambda$ or dimensional regularization. Renormalization then rewrites the answer in terms of physical or renormalized parameters. A typical one-loop expression has the schematic form

$$
I(\Lambda)=\text{divergent local terms}+\text{finite nonlocal terms}.
$$

The divergent local terms can be absorbed into coefficients already multiplying local operators in the Lagrangian, at least in a renormalizable theory. The finite nonlocal terms are physical predictions once a renormalization prescription has fixed the parameters.

This page is intentionally a **preview**. It explains why divergent loop integrals appear and why the next major section of qft.org must be Renormalization, RG, and EFT. It does not attempt to prove all-order renormalizability, develop the Callan–Symanzik equation, or teach Wilsonian effective field theory in full.

Coleman's chapter “Coping with infinities” asks exactly the right foundational question: whether renormalization is necessary and sufficient to remove infinities, after first showing a logarithmically divergent one-loop vertex graph and a counterterm that cancels it (Coleman 2019, ch. 25). Weinberg's general renormalization chapter frames the modern view: renormalizable theories are still special, but nonrenormalizable interactions are also part of the effective-field-theory description of low-energy physics (Weinberg 1995, Vol. I, ch. 12). Srednicki introduces loop corrections to the propagator and vertex before moving to higher-order corrections and renormalizability (Srednicki 2007, §§14–18). Zee emphasizes the same power-counting distinction in a deliberately physical style (Zee 2010, Part III).

## Prerequisites

You should know [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/), [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/), [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/), [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [iε Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/), and [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/).

## The core problem

A tree diagram is algebraic once the external momenta are specified. A loop diagram is different: some momenta are not fixed by momentum conservation. They are integrated over.

For a one-loop two-point diagram, the schematic structure is

$$
\Pi(p)\sim\int\frac{d^4k}{(2\pi)^4}\,
\frac{\text{numerator}(k,p)}{\text{propagators}(k,p)}.
$$

The variable $k$ is an internal four-momentum. Perturbation theory says to integrate over all $k$. At large $k$, propagators fall as powers of $k$, vertices may add powers of $k$, and the measure contributes $d^4k$. The UV question is brutally simple:

```txt
Does the large-momentum tail of the loop integral converge?
```

<figure class="doc-figure" style="--figure-width: 48rem;">

![UV loop divergence, regularization, and counterterms](/figures/foundations/uv-divergence-renormalization-map.svg)

<figcaption>

A loop integral samples arbitrarily large internal momentum $k$. A regulator makes the large-$k$ region explicit, often producing terms such as $a\Lambda^2+b\log\Lambda$. Renormalization absorbs the local cutoff-dependent pieces into counterterms such as $\delta m^2$, $\delta Z$, and $\delta\lambda$, leaving finite Green functions after renormalization conditions are imposed at a scale $\mu$.

</figcaption>
</figure>

The word “divergent” is often used too quickly. More precisely, the unregularized expression is not yet a well-defined number or distribution. You should first regulate it, calculate with the regulator in place, and only then ask whether physical quantities can be made independent of the regulator.

:::note[Boundary of this page]
Foundations tells you why loops reveal short-distance singularities. Renormalization, RG, and EFT tell you what those singularities mean, how parameters run with scale, why universality appears, and why nonrenormalizable interactions are predictive at low energies.
:::

## A scalar one-loop example

Consider the real scalar theory in four spacetime dimensions,

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

At one loop, the tadpole correction to the scalar two-point function contains the integral

$$
-i\Sigma_{\rm tad}
=\frac{-i\lambda}{2}
\int\frac{d^4k}{(2\pi)^4}\,
\frac{i}{k^2-m^2+i\epsilon}.
$$

The factor $1/2$ is the symmetry factor for the tadpole. The exact sign convention is less important here than the high-momentum behavior. After Wick rotation and a Euclidean cutoff, the basic integral is

$$
I_E(\Lambda)
=\int_{|k_E|<\Lambda}\frac{d^4k_E}{(2\pi)^4}
\frac{1}{k_E^2+m^2}.
$$

Using $d^4k_E=2\pi^2 k^3dk$, we get

$$
I_E(\Lambda)
=\frac{1}{8\pi^2}\int_0^\Lambda dk\,
\frac{k^3}{k^2+m^2}.
$$

The integral is elementary:

$$
\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}
=\frac12\left[\Lambda^2-m^2\log\left(\frac{\Lambda^2+m^2}{m^2}\right)\right].
$$

Therefore

$$
\boxed{
I_E(\Lambda)
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\left(\frac{\Lambda^2+m^2}{m^2}\right)
\right].
}
$$

For large cutoff,

$$
I_E(\Lambda)
=\frac{\Lambda^2}{16\pi^2}
-\frac{m^2}{16\pi^2}\log\frac{\Lambda^2}{m^2}
+O(\Lambda^0).
$$

This is a UV divergence. It is not caused by external particles being energetic. It appears even in a low-energy two-point function because the loop integrates over arbitrarily short-distance fluctuations.

The divergent contribution is proportional to $\phi^2$ in the effective action, so it has the same local form as the mass term already present in the Lagrangian. That is why the tadpole divergence is called a **mass renormalization**.

## Local divergences and counterterms

Perturbation theory teaches us to split the Lagrangian into renormalized terms and counterterms. For the scalar theory above, write schematically

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
+\mathcal L_{\rm ct},
$$

with

$$
\boxed{
\mathcal L_{\rm ct}
=\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4
-\delta\Omega.
}
$$

Here $\delta\Omega$ is a vacuum-energy counterterm. The counterterms are not optional decorations; they are the local terms needed to express bare quantities in terms of renormalized ones.

The slogan is:

```txt
Regularization exposes cutoff dependence.
Counterterms absorb local cutoff dependence.
Renormalization conditions define the finite parameters.
```

The local nature of UV divergences is crucial. A divergence from the region $k\gg p_i,m$ cannot depend on the detailed long-distance structure of the diagram. Its dependence on external momenta can be expanded in a polynomial:

$$
\text{UV part}
= a_0(\Lambda)+a_2(\Lambda)p^2+a_4(\Lambda)p^4+\cdots.
$$

In position space, powers of $p$ are derivatives. Thus divergent UV pieces correspond to local operators:

$$
1,\qquad \phi^2,\qquad (\partial\phi)^2,\qquad \phi^4,\qquad \phi\Box^2\phi,\ldots
$$

A renormalizable theory is one in which, at every order, only finitely many operator structures are needed to absorb all UV divergences. More modernly, an effective field theory includes all allowed local operators, but higher-dimension operators are suppressed by powers of a heavy scale.

## Power counting

Power counting estimates the large-momentum behavior of a diagram before doing the integral.

In four dimensions, each loop integration contributes four powers of momentum:

$$
\int d^4k\sim k^4.
$$

Each scalar propagator contributes two inverse powers:

$$
\frac{i}{k^2-m^2+i\epsilon}\sim k^{-2}.
$$

For a scalar diagram with $L$ loops and $I$ internal scalar lines, with no derivative vertices, the superficial degree of divergence is

$$
D=4L-2I.
$$

The number $D$ means the following: when all loop momenta are scaled uniformly, $k\mapsto \rho k$, the diagram behaves like a power $\rho^D$. If $D>0$, the diagram is superficially power divergent. If $D=0$, it is superficially logarithmically divergent. If $D<0$, the overall large-momentum region is superficially convergent.

For connected $\lambda\phi^4$ diagrams, the graph identities are

$$
4V=2I+E,
\qquad
L=I-V+1,
$$

where $V$ is the number of quartic vertices and $E$ is the number of external lines. Combining these gives

$$
\boxed{D=4-E.}
$$

Thus, in four-dimensional $\phi^4$ theory:

| External legs | Superficial degree | Counterterm type |
| --- | ---: | --- |
| $E=0$ | $D=4$ | vacuum energy |
| $E=2$ | $D=2$ | mass and field-strength terms |
| $E=4$ | $D=0$ | quartic coupling |
| $E\ge6$ | $D<0$ | no new superficial divergence |

This table is the first glimpse of renormalizability. The divergent structures match the operators already present in

$$
1,
\qquad
\phi^2,
\qquad
(\partial\phi)^2,
\qquad
\phi^4.
$$

That does **not** mean every diagram with $E\ge6$ is harmless. It means the overall divergence from all loop momenta going large together is absent. A diagram may still contain divergent subdiagrams. This is why real renormalization theory needs recursive subtractions, not just one line of power counting.

## A logarithmic four-point example

The one-loop correction to four-scalar scattering contains an integral of the form

$$
I_4(p)
=\int\frac{d^4k}{(2\pi)^4}
\frac{i}{k^2-m^2+i\epsilon}
\frac{i}{(k+p)^2-m^2+i\epsilon}.
$$

At large $k$,

$$
I_4(p)\sim\int d^4k\,\frac{1}{k^4}.
$$

With a Euclidean cutoff this behaves like

$$
\int^\Lambda dk\,\frac{k^3}{k^4}
=\int^\Lambda\frac{dk}{k}
\sim\log\Lambda.
$$

So the four-point one-loop graph is logarithmically divergent. Its divergent part has the same local form as the original $\phi^4$ vertex, so it is absorbed into $\delta\lambda$.

The finite remainder depends on external momenta. That momentum dependence is not removed by a local counterterm. It is the beginning of real quantum dynamics: scattering amplitudes know about loops through logarithms, thresholds, imaginary parts, and branch cuts.

## Regularization is not renormalization

A **regulator** is a temporary device that makes integrals well-defined. Common examples include:

| Regulator | Basic idea | Strength | Caveat |
| --- | --- | --- | --- |
| Momentum cutoff | Restrict $|k|<\Lambda$ | intuitive short-distance scale | can obscure Lorentz or gauge symmetry |
| Pauli–Villars | subtract heavy fictitious propagators | preserves Lorentz covariance in simple cases | introduces unphysical regulator fields |
| Dimensional regularization | continue integrals to $d=4-\epsilon$ | excellent for gauge theories | power divergences are hidden rather than displayed |
| Lattice cutoff | replace spacetime by a lattice | nonperturbative definition in Euclidean QFT | breaks continuous spacetime symmetry at finite spacing |

A **renormalization prescription** tells you how to define the finite parameters. For example, one may impose conditions such as

$$
G_2^{-1}(p^2=m^2)=0,
\qquad
\left.\frac{dG_2^{-1}}{dp^2}\right|_{p^2=m^2}=1,
\qquad
\Gamma^{(4)}(p_i\text{ at reference point})=-\lambda.
$$

These conditions define the physical mass, field normalization, and coupling in an on-shell-like scheme. Other schemes, such as minimal subtraction, define parameters differently. The finite intermediate expressions may look different, but physical observables agree when expressed in terms of physical input data.

The regulator should disappear from final physical predictions. The renormalization scale $\mu$, however, usually remains as a bookkeeping scale: changing $\mu$ changes the renormalized parameters in a compensating way. That compensation is the renormalization group.

## Dimensional regularization preview

With dimensional regularization, a logarithmically divergent integral often appears as a pole at $d=4$:

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2+m^2)^2}
\sim
\frac{1}{16\pi^2}\left(\frac{2}{\epsilon}+\text{finite}\right),
\qquad
\epsilon=4-d.
$$

The pole $1/\epsilon$ plays the role of the logarithmic UV divergence. Minimal subtraction removes the pole; modified minimal subtraction removes a conventional combination of the pole and constants. The result is compact and symmetry-friendly, which is why dimensional regularization is the standard tool in perturbative gauge theory.

But dimensional regularization can hide power divergences. For example, quadratic cutoff sensitivity may not appear as an explicit $\Lambda^2$ term. This is not magic. It reflects the regulator's treatment of scale-free power divergences. When discussing naturalness, thresholds, Wilsonian matching, or sensitivity to heavy physics, one must remember what the regulator is showing and what it is suppressing.

## Renormalizable versus nonrenormalizable

In four dimensions, the engineering dimension of the scalar field is

$$
[\phi]=1,
$$

and the Lagrangian density has dimension four. An operator $\mathcal O_i$ of dimension $\Delta_i$ appears as

$$
\mathcal L\supset g_i\mathcal O_i,
\qquad
[g_i]=4-\Delta_i.
$$

The old terminology is:

| Operator dimension | Coupling dimension | Traditional name |
| ---: | ---: | --- |
| $\Delta_i<4$ | positive | superrenormalizable |
| $\Delta_i=4$ | zero | renormalizable |
| $\Delta_i>4$ | negative | nonrenormalizable |

The word “nonrenormalizable” is historically loaded. It does **not** mean useless. It means that, if you insist on using the theory at arbitrarily high energy and at arbitrarily high order, infinitely many counterterms are needed. As an effective field theory below a scale $M$, the same interactions are organized as a controlled expansion:

$$
\mathcal L_{\rm EFT}
=\mathcal L_{\le4}
+\sum_{\Delta_i>4}\frac{c_i}{M^{\Delta_i-4}}\mathcal O_i.
$$

At energies $E\ll M$, higher-dimension operators are suppressed by powers of $E/M$. This is why nonrenormalizable interactions are not a pathology in the modern view. They are the expected imprint of short-distance physics on long-distance experiments.

## What this preview does not yet explain

This page has deliberately avoided several important things.

It has not proved that all divergences can be removed in a given theory. That proof requires a careful recursive treatment of subdivergences and overlapping divergences. Power counting is a diagnostic, not a complete proof.

It has not explained running couplings. Once a renormalized coupling is defined at a scale $\mu$, changing $\mu$ leads to a beta function. That is the doorway to asymptotic freedom, Landau poles, fixed points, and critical phenomena.

It has not developed Wilson's picture. Wilsonian renormalization explains renormalization by integrating out short-distance modes and following the flow of all local operators in theory space. This is the conceptual bridge from perturbative infinities to universality.

It has not addressed gauge theories. Gauge invariance restricts counterterms and relates renormalization constants through Ward or Slavnov–Taylor identities. Regulating a gauge theory while preserving its symmetry is an art in its own right.

It has not addressed infrared divergences. UV divergences come from high momentum. Infrared divergences come from low momentum or long distance, especially in theories with massless particles. They require different physics.

The point of this page is narrower and sharper:

```txt
Loops reveal short-distance singularities.
Locality turns those singularities into local counterterms.
Renormalization fixes the finite meaning of the parameters.
The renormalization group explains how the description changes with scale.
```

## Common pitfalls

**Mistaking virtual momentum for measured momentum.** A low-energy process can contain a loop integral over arbitrarily high internal momentum. The external momenta and loop momenta are different things.

**Calling every infinity a disaster.** An unregulated divergent integral is not a prediction. The predictive question is whether the regulator dependence can be absorbed into a finite set, or controlled hierarchy, of parameters.

**Confusing regularization with physics.** A cutoff, Pauli–Villars field, dimensional continuation, or lattice spacing is usually a calculational device. Physical statements should not depend on arbitrary regulator details.

**Thinking counterterms are cheating.** Counterterms express the fact that the parameters in the bare Lagrangian are not directly measured quantities. The measured mass and coupling are fixed by renormalization conditions.

**Forgetting subdivergences.** Superficial convergence of the whole graph does not rule out divergent subgraphs. This is where naive power counting stops and real renormalization theory begins.

**Treating “nonrenormalizable” as “bad.”** In modern QFT, nonrenormalizable operators are essential. They are organized by EFT power counting and encode short-distance physics through suppressed local operators.

## Relations to other pages

- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) introduces the cubic and quartic vertices whose loop corrections first produce UV divergences.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains why vacuum bubbles cancel from normalized correlators before we worry about UV divergences in the remaining connected diagrams.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) packages loop corrections into 1PI vertices; counterterms are often most cleanly discussed at the level of 1PI functions.
- [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains why regularization is part of defining functional integrals, not an optional afterthought.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) shows how exact propagators encode physical mass poles and continua; renormalization determines how perturbation theory realizes those structures.
- [Renormalization Basics](/renormalization-rg-eft/renormalization-basics/) will develop counterterms, renormalization conditions, and subtraction schemes systematically.
- [Loop Calculations](/perturbative-qft/loop-calculations/) will develop practical one-loop technology such as Feynman parameters, Wick rotation, dimensional regularization, and tensor reduction.
- [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) will explain why higher-dimension operators are predictive at low energies rather than simply “bad.”

## Research status

The existence of UV divergences in perturbative loop integrals and their cancellation by local counterterms in renormalizable QFTs are textbook-standard. The exact all-order proofs, the Wilsonian interpretation, and the EFT reorganization belong to the later Renormalization, RG, and EFT group. This page is a conceptual bridge, not a substitute for that group.

## Exercises

### Exercise 1: Tadpole degree of divergence

Estimate the superficial UV behavior of

$$
I=\int\frac{d^4k}{(2\pi)^4}\frac{1}{k^2-m^2+i\epsilon}.
$$

Is it quadratically, logarithmically, or superficially convergent?

<details>
<summary><strong>Solution</strong></summary>

At large $k$,

$$
\frac{1}{k^2-m^2+i\epsilon}\sim \frac1{k^2}.
$$

The four-dimensional measure behaves as $d^4k\sim k^3dk$, so

$$
I_{\rm UV}\sim\int^\Lambda dk\,\frac{k^3}{k^2}
=\int^\Lambda dk\,k
\sim \Lambda^2.
$$

The integral is quadratically divergent by cutoff power counting.

</details>

### Exercise 2: The one-loop four-point integral

Show by power counting that

$$
I_4(p)=\int\frac{d^4k}{(2\pi)^4}
\frac{1}{(k^2-m^2+i\epsilon)((k+p)^2-m^2+i\epsilon)}
$$

is logarithmically divergent.

<details>
<summary><strong>Solution</strong></summary>

For $k\gg p,m$, each propagator contributes $1/k^2$, so the integrand contributes $1/k^4$. The measure contributes $k^3dk$, hence

$$
I_{4,\rm UV}\sim\int^\Lambda dk\,\frac{k^3}{k^4}
=\int^\Lambda\frac{dk}{k}
\sim \log\Lambda.
$$

Therefore the integral is logarithmically divergent.

</details>

### Exercise 3: Derive the scalar cutoff integral

Evaluate

$$
I_E(\Lambda)=\int_{|k_E|<\Lambda}\frac{d^4k_E}{(2\pi)^4}\frac{1}{k_E^2+m^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Use four-dimensional spherical coordinates:

$$
d^4k_E=2\pi^2k^3dk.
$$

Then

$$
I_E(\Lambda)=\frac{1}{8\pi^2}\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}.
$$

Write

$$
\frac{k^3}{k^2+m^2}=k-\frac{m^2k}{k^2+m^2}.
$$

Therefore

$$
\int_0^\Lambda dk\,\frac{k^3}{k^2+m^2}
=\frac{\Lambda^2}{2}
-\frac{m^2}{2}\log\left(\frac{\Lambda^2+m^2}{m^2}\right),
$$

so

$$
I_E(\Lambda)=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\left(\frac{\Lambda^2+m^2}{m^2}\right)
\right].
$$

</details>

### Exercise 4: Power counting in quartic scalar theory

For connected $\phi^4$ diagrams in four dimensions, use

$$
4V=2I+E,
\qquad
L=I-V+1,
$$

to show that $D=4-E$.

<details>
<summary><strong>Solution</strong></summary>

The superficial degree of divergence is

$$
D=4L-2I.
$$

Using $L=I-V+1$ gives

$$
D=4(I-V+1)-2I=2I-4V+4.
$$

From $4V=2I+E$, we have

$$
2I=4V-E.
$$

Substitute this into $D$:

$$
D=(4V-E)-4V+4=4-E.
$$

</details>

### Exercise 5: Why a φ⁶ interaction is nonrenormalizable in four dimensions

In four dimensions, $[\phi]=1$. What is the mass dimension of the coupling $g_6$ in

$$
\mathcal L_{\rm int}=-\frac{g_6}{6!}\phi^6?
$$

What does this imply in the old power-counting sense?

<details>
<summary><strong>Solution</strong></summary>

The operator $\phi^6$ has dimension

$$
[\phi^6]=6.
$$

Since the Lagrangian density has dimension four,

$$
[g_6]=4-6=-2.
$$

The coupling has negative mass dimension, so $\phi^6$ is nonrenormalizable by the old power-counting classification. In EFT language, we would write

$$
g_6\sim \frac{c_6}{M^2},
$$

and treat it as a higher-dimension operator suppressed at energies $E\ll M$.

</details>

### Exercise 6: Local versus nonlocal dependence

Why can a UV-divergent part be absorbed into local counterterms, while finite threshold behavior cannot generally be removed by local counterterms?

<details>
<summary><strong>Solution</strong></summary>

The UV-divergent part comes from loop momenta much larger than all external momenta and masses:

$$
k\gg p_i,m.
$$

In that region, the integrand can be expanded in powers of external momenta and masses. After integration, the divergent pieces multiply polynomials in $p_i$. Polynomials in momentum correspond to local operators in position space.

Threshold behavior, branch cuts, and imaginary parts come from loop momenta where internal lines can go on shell or where long-distance propagation matters. Such dependence is non-polynomial in external momenta, so it cannot be canceled by local counterterms. It is part of the physical amplitude.

</details>

## Sources and further reading

- N. N. Bogoliubov and O. S. Parasiuk, “On the Multiplication of the Causal Function in the Quantum Theory of Fields,” *Acta Mathematica* **97** (1957), 227–266; K. Hepp, “Proof of the Bogoliubov–Parasiuk theorem on renormalization,” *Communications in Mathematical Physics* **2** (1966), 301–326; W. Zimmermann, “Convergence of Bogoliubov's Method of Renormalization in Momentum Space,” *Communications in Mathematical Physics* **15** (1969), 208–234, for the BPHZ renormalization framework.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974), 75–199, for the Wilsonian viewpoint.
- Mark Srednicki, *Quantum Field Theory*, §§14–18, for loop corrections and renormalizability in scalar theory, and §29 for effective field theory.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 25, for regularization, the BPHZ algorithm, and power counting; chs. 9–10 for the first perturbative divergences and mass renormalization.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, Part III, for a physically motivated introduction to cutoffs, counterterms, and power counting; ch. VIII.3 for effective field theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for general renormalization theory and the effective-field-theory interpretation.

## Version history

- **2026-05-23:** Initial qft.org preview of ultraviolet divergences: loop momentum, cutoff dependence, scalar one-loop examples, counterterms, superficial degree of divergence, regularization versus renormalization, and EFT interpretation.
