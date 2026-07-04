---
title: "String Tension"
description: "Defines the confining string tension from Wilson loops and static potentials, explains flux-tube physics, and states when the quantity is sharp."
sidebar:
  label: "String Tension"
  order: 5
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov; Srednicki ch. 82; Shifman chs. 1 and 9; lattice gauge theory literature."
topics:
  - string tension
  - flux tubes
  - Wilson loops
  - static potential
  - confinement
  - effective string theory
  - lattice gauge theory
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - string-tension
  - flux-tubes
  - wilson-loops
researchStatus:
  established:
    - "A stable Wilson-loop area law defines a string tension as the coefficient of the linear static potential in the corresponding probe sector."
  active:
    - "The spectrum, interactions, and universality of confining flux tubes remain active topics, especially for k-strings, [large-N limits](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/), and gauge theories with matter."
---

## Summary

The **string tension** $\sigma$ is the energy per unit length of a stable confining flux tube. It is equivalently the coefficient of the area law for a large Wilson loop or the coefficient of the linear term in the static potential:

$$
\langle W_R(C_{r,\mathcal T})\rangle
\sim e^{-\sigma_R r\mathcal T},
\qquad
V_R(r)\sim \sigma_R r.
$$

The string tension is a physical infrared scale. In four spacetime dimensions it has mass dimension two,

$$
[\sigma]=2,
$$

so $\sqrt{\sigma}$ is a mass scale. Lattice gauge theory often quotes dimensionless combinations such as $a^2\sigma$, $m_{0^{++}}/\sqrt{\sigma}$, or $T_c/\sqrt{\sigma}$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A static source and antisource connected by a confining flux tube, with the linear potential and effective string correction shown schematically.](/figures/nonperturbative-qft/string-tension-flux-tube.svg)

<figcaption>

The string tension $\sigma$ measures the energy per unit length of the stable flux tube sourced by an unscreened Wilson line. At long distance the leading potential is $V(r)\sim \sigma r$, while transverse fluctuations can produce universal subleading terms under suitable assumptions.

</figcaption>
</figure>

A warning belongs in the definition: a string tension is sharp only in a sector where the flux tube is asymptotically stable. In full QCD with dynamical fundamental quarks, the fundamental string can break. One can still discuss an intermediate-distance string tension, but the strict $r\to\infty$ fundamental Wilson-loop string tension vanishes.

## Prerequisites

You should know [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), and [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/).

For extraction methods, it helps to know [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), and [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/).

## Core idea

Confinement is not merely that the potential is “large.” It is that the lowest-energy field configuration between appropriate external probes contains a tube of flux whose energy grows with its length.

If the tube has approximately constant transverse size and approximately constant energy density per unit length, then

$$
E_{\rm tube}(r)\approx \sigma r.
$$

The same statement appears in Euclidean path integrals. A static source–antisource pair separated by $r$ and propagated for Euclidean time $\mathcal T$ sweeps out a worldsheet of area $r\mathcal T$. If the worldsheet costs action proportional to area, then

$$
\langle W(C_{r,\mathcal T})\rangle
\sim e^{-\sigma r\mathcal T}.
$$

Thus $\sigma$ is both a Hamiltonian quantity and a Euclidean-loop quantity. The two interpretations are tied together by spectral decomposition.

## Definition from the static potential

For a rectangular Wilson loop in representation $R$, define the static potential by

$$
V_R(r)=-\lim_{\mathcal T\to\infty}
\frac{1}{\mathcal T}
\log\langle W_R(C_{r,\mathcal T})\rangle_{\rm ren}.
$$

If the large-distance potential has the form

$$
V_R(r)=\sigma_R r + c_R + o(r),
\qquad r\to\infty,
$$

then

$$
\sigma_R=\lim_{r\to\infty}\frac{V_R(r)}{r}.
$$

Equivalently,

$$
\sigma_R=-\lim_{r,\mathcal T\to\infty}
\frac{1}{r\mathcal T}
\log\langle W_R(C_{r,\mathcal T})\rangle_{\rm ren},
$$

with the limits taken in a regime where boundary, cusp, and finite-aspect-ratio effects do not contaminate the area coefficient.

The additive constant $c_R$ includes static-source self-energies and scheme-dependent pieces. The slope $\sigma_R$, when nonzero and stable, is the physical long-distance tension.

## Units and normalization

In $d$ spacetime dimensions, an action is dimensionless and an area has dimension $-2$, so string tension has dimension

$$
[\sigma]=2
$$

in mass units, independent of $d$. On a lattice with spacing $a$, the dimensionless tension is

$$
\hat\sigma=a^2\sigma.
$$

Taking a continuum limit while keeping a physical string tension fixed means

$$
\hat\sigma\to0
\qquad
\text{as}
\qquad
 a\to0.
$$

This is a useful sanity check. In lattice units, the flux tube becomes many lattice spacings long and the dimensionless tension shrinks, even though $\sigma$ in physical units stays finite.

String tension is often used to set the scale in pure gauge simulations. Since pure Yang–Mills has no experimentally measured quark masses or decay constants, ratios such as

$$
\frac{m_{0^{++}}}{\sqrt{\sigma}},
\qquad
\frac{T_c}{\sqrt{\sigma}},
\qquad
\frac{\sigma_k}{\sigma_1}
$$

are more invariant than isolated dimensionful numbers.

## Flux-tube picture

A confining flux tube is not a classical string added by hand. It is a collective excitation of the gauge-field vacuum in the presence of external sources.

The physical picture is this:

1. The external probes force electric flux into a nontrivial center-charge sector.
2. The vacuum does not allow that flux to spread indefinitely at low energy.
3. The flux localizes into a tube of finite transverse thickness.
4. Translating the probes farther apart adds more tube length.
5. The energy therefore grows linearly.

The finite thickness is important. The flux tube is string-like only at distances much longer than its width. At shorter distances, the field configuration knows about the microscopic gauge theory, Coulombic behavior, and representation-dependent details.

## Effective string expansion

A long stable flux tube has transverse fluctuations. At distances much longer than its thickness, these fluctuations can often be described by an effective string theory. The simplest universal prediction for an open string between static sources is the Lüscher correction,

$$
V(r)=\sigma r + c - \frac{\pi(d-2)}{24r}+O\!\left(\frac{1}{r^3}\right),
$$

where $d$ is the spacetime dimension and $d-2$ counts transverse massless modes of the flux tube. In four spacetime dimensions this term is

$$
-\frac{\pi}{12r}.
$$

This formula is powerful but has assumptions. It applies to a long, stable, unbroken flux tube whose only low-energy worldsheet modes are the transverse Goldstone modes associated with broken translations. Extra orientational, fermionic, topological, or boundary modes can change the long-string spectrum.

The effective string viewpoint also predicts excitations of the flux tube above its ground state. In lattice simulations, these appear as excited static potentials or torelon spectra. They are not elementary fundamental strings; they are infrared descriptions of gauge-theory flux tubes.

## Extraction from Wilson loops

The direct Wilson-loop extraction uses

$$
\langle W(r,\mathcal T)\rangle
\approx A(r)e^{-V(r)\mathcal T}
$$

for large $\mathcal T$. A practical analysis often improves ground-state overlap by using smeared or variational operators rather than a single thin Wilson loop.

On a lattice, a classic area-law estimator is the Creutz ratio. For rectangular loops in lattice units,

$$
\chi(R,T)
=-\log\left[
\frac{W(R,T)W(R-1,T-1)}{W(R,T-1)W(R-1,T)}
\right].
$$

If

$$
W(R,T)\sim e^{-\hat\sigma RT-\hat\mu(2R+2T)},
$$

then the perimeter terms cancel and

$$
\chi(R,T)\to\hat\sigma
$$

at large $R,T$, up to finite-size, effective-string, and excited-state corrections. This is not the only modern method, but it is conceptually excellent: it shows how an area coefficient can be isolated from perimeter contamination.

Another method uses a flux tube winding around a spatial circle of length $L$. The corresponding state is often called a torelon. For a long closed flux tube,

$$
E_{\rm tor}(L)\approx \sigma L - \frac{\pi(d-2)}{6L}+\cdots,
$$

again under effective-string assumptions. This gives an independent way to extract $\sigma$.

## Representation dependence and N-ality

In pure $SU(N)$ Yang–Mills theory, not every representation gives a distinct asymptotic string. Gluons are dynamical adjoint particles. They can screen representation labels by tensoring with adjoints, but they cannot change the representation’s charge under the center $\mathbb Z_N$.

The asymptotic string sector is therefore organized by [N-ality](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/):

$$
k_R \in \mathbb Z_N.
$$

Representations with the same nonzero N-ality can flow to the same asymptotic string sector after gluon screening. Representations with zero N-ality can be screened to a singlet and need not have an asymptotic string tension.

One often writes

$$
\sigma_k
$$

for the tension of the stable string carrying center charge $k$. These are called $k$-strings. Their ratios $\sigma_k/\sigma_1$ are nontrivial nonperturbative data. Proposed approximate patterns, such as Casimir scaling or sine-law scaling, are useful but should not be confused with general theorems.

## String breaking and metastable tensions

When dynamical matter can screen the probe, the strict asymptotic string tension for that probe is zero:

$$
\lim_{r\to\infty}\frac{V(r)}{r}=0.
$$

This does not erase the intermediate flux tube. The potential can still behave as

$$
V(r)\approx \sigma_{\rm eff} r + c
$$

for a broad range of distances before string breaking. In such cases $\sigma_{\rm eff}$ is a useful intermediate-distance or phenomenological string tension, not an exact asymptotic order parameter.

This distinction is crucial in QCD-like theories. The static quark potential can show a linear regime, and flux tubes are visible in suitable observables, but light quark–antiquark pair creation eventually screens a fundamental source–antisource pair.

The same distinction appears in many gauge-Higgs systems. A linearly rising potential may be an excited-string channel, while the true ground state is screened at sufficiently long distance.

## Relation to the mass gap

A nonzero string tension is not the same as a mass gap, but the two are related in confining pure gauge theories.

If the theory has a stable flux tube, then $\sqrt{\sigma}$ is a mass scale. Pure Yang–Mills is also expected to have a glueball spectrum with a lowest mass $m_{0^{++}}$ of order $\sqrt{\sigma}$. Lattice studies often report ratios of glueball masses to $\sqrt{\sigma}$.

However, logical implications require care.

A gapped theory need not confine. A gauge theory can have a mass gap because of Higgs screening or topological order without a Wilson-loop area law for a given probe. Conversely, an area law for a regulated lattice theory is strong evidence of a confining phase, but proving the continuum [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/) is a much sharper mathematical task.

String tension is therefore best viewed as one diagnostic in a network: it is tied to Wilson loops and flux tubes, while the mass gap is tied to correlation functions and spectra.

## Common mistakes

**Mistake 1: Treating $\sigma$ as representation-independent.** In non-Abelian gauge theory, short-distance potentials depend on representation, and asymptotic tensions depend on screenable charges such as N-ality.

**Mistake 2: Extracting $\sigma$ from too-short distances.** A linear-looking potential at intermediate $r$ may contain Coulombic, self-energy, lattice-artifact, and excited-state contributions. The asymptotic string tension is a long-distance quantity.

**Mistake 3: Ignoring string breaking.** In theories with dynamical fundamental matter, the strict asymptotic fundamental string tension vanishes even when an intermediate flux tube is physically important.

**Mistake 4: Confusing the flux tube with a fundamental string.** Effective string theory describes long-distance fluctuations of a gauge-theory object. It is an infrared approximation, not a microscopic definition.

**Mistake 5: Forgetting perimeter and cusp renormalization.** Wilson loops require renormalization. The string tension is the infrared area coefficient after local line effects are separated.

## Research status

- **Established:** In a sector with a stable Wilson-loop area law, the string tension is the coefficient of both the area law and the asymptotically linear static potential.
- **Established:** Pure non-Abelian lattice gauge theories provide strong numerical evidence for nonzero string tensions and glueball spectra in the continuum limit.
- **Established:** Dynamical screening matter can make the asymptotic string tension vanish for a probe even when an intermediate flux tube remains useful.
- **Active:** The detailed worldsheet theory of confining flux tubes, including massive modes and universality beyond the Lüscher term, remains an active topic.
- **Active:** $k$-string tensions, large-$N$ scaling, and the relation between flux tubes, center symmetry, and generalized symmetries continue to connect lattice gauge theory with continuum analysis.

## Relation to other topics

This page completes the basic Wilson-loop chain:

$$
\text{Wilson loop}
\longrightarrow
\text{area law}
\longrightarrow
\text{linear potential}
\longrightarrow
\text{string tension}.
$$

The previous pages are [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) and [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/). [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) explains the related but distinct spectral question.

The companion page [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/) explains the field configuration and long-string effective theory behind the tension $\sigma$. The mechanism pages are [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/), where $\sigma a^2$ arises from plaquette counting, [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/), where the string tension is the tension of a dual-photon wall ending on a Wilson loop, and [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/), which compares the major proposed dynamical pictures.

## Exercises

### Exercise 1: Creutz ratio cancellation

Assume rectangular Wilson loops obey

$$
W(R,T)=\exp[-\hat\sigma RT-\hat\mu(2R+2T)]
$$

in lattice units. Show that the Creutz ratio

$$
\chi(R,T)
=-\log\left[
\frac{W(R,T)W(R-1,T-1)}{W(R,T-1)W(R-1,T)}
\right]
$$

equals $\hat\sigma$.

<details>
<summary><strong>Solution</strong></summary>

Compute the exponent in the ratio. The area contribution is

$$
-\hat\sigma\big[RT+(R-1)(T-1)-R(T-1)-(R-1)T\big].
$$

The bracket equals

$$
RT+(RT-R-T+1)-(RT-R)-(RT-T)=1.
$$

Thus the ratio contains $e^{-\hat\sigma}$. The perimeter terms cancel because

$$
(2R+2T)+2(R-1+T-1)-2(R+T-1)-2(R+T-1)=0.
$$

Therefore

$$
\chi(R,T)=-\log(e^{-\hat\sigma})=\hat\sigma.
$$

</details>

### Exercise 2: Dimension of string tension

Using $c=\hbar=1$, determine the mass dimension of $\sigma$ in

$$
V(r)=\sigma r.
$$

<details>
<summary><strong>Solution</strong></summary>

Energy has mass dimension $1$, and distance has mass dimension $-1$. Therefore

$$
[V]=1,
\qquad
[r]=-1.
$$

Since $V=\sigma r$,

$$
[\sigma]+[r]=1
\quad\Rightarrow\quad
[\sigma]-1=1.
$$

Thus

$$
[\sigma]=2.
$$

</details>

### Exercise 3: String breaking and asymptotic tension

Suppose a static potential behaves as $V(r)=\sigma r$ for $r<r_{\rm br}$ but approaches a constant $E_{\rm screen}$ for $r\to\infty$. What is

$$
\lim_{r\to\infty}\frac{V(r)}{r}?
$$

<details>
<summary><strong>Solution</strong></summary>

If $V(r)\to E_{\rm screen}$ as $r\to\infty$, then

$$
\lim_{r\to\infty}\frac{V(r)}{r}
=
\lim_{r\to\infty}\frac{E_{\rm screen}}{r}=0.
$$

Thus the strict asymptotic string tension for that probe is zero, even though an intermediate-distance linear regime can have a nonzero effective tension.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapter 82, for Wilson loops, static potentials, perimeter laws, and confinement diagnostics.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters 1 and 9, for phases of gauge theories, string tension, string breaking, and large-$N$ confinement.
- A. M. Polyakov, *Gauge Fields and Strings*, especially strong-coupling expansion, confinement analogies, compact QED, loop dynamics, and large-$N$ expansion.

### Deeper references

- K. Wilson, “Confinement of Quarks,” for the Wilson-loop criterion.
- M. Lüscher, K. Symanzik, and P. Weisz, and later effective-string literature, for universal long-string corrections.
- J. Kogut, “An Introduction to Lattice Gauge Theory and Spin Systems,” for lattice strong-coupling and Wilson-loop methods.
- J. Greensite, *An Introduction to the Confinement Problem*, for modern lattice and continuum perspectives on string tension and flux tubes.

## Version history

- **2026-06-27:** Initial polished page. Added definitions from Wilson loops and static potentials, flux-tube interpretation, lattice extraction by Creutz ratios, N-ality dependence, string-breaking caveats, effective string corrections, and exercises.
- **2026-06-27:** Linked the dedicated center-symmetry page for the N-ality discussion.
- **2026-06-27:** Linked strong-coupling and compact-QED mechanisms for generating string tension.
- **2026-06-27:** Linked Flux Tubes and Mass Gap in Gauge Theory as companion pages.
- **2026-06-27:** Linked Large-N Confinement for k-string and flux-tube scaling.
