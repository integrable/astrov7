---
title: "Loops and Locality"
description: "Why the ultraviolet part of a loop diagram is local, why counterterms have the form of local operators, and where nonlocal physical effects enter."
sidebar:
  label: "Loops and Locality"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§14–20 and §§27–29; Schwartz chs. 16–23; Weinberg Vol. I ch. 12; Wilson and Kogut 1974; Zinn-Justin, perturbative renormalization chapters."
topics:
  - loop diagrams
  - locality
  - ultraviolet divergences
  - counterterms
  - derivative expansion
  - renormalization
canonicalTopics:
  - loop-divergence
  - locality
  - counterterm
  - derivative-expansion
researchStatus:
  established:
    - "The ultraviolet part of a loop subgraph in a local QFT is organized by local operators, which is the structural reason local counterterms suffice in perturbative renormalization."
  active:
    - "The same locality principle becomes technically subtle in gauge theories, overlapping UV/IR singularities, curved backgrounds, effective theories with many operator bases, and nonperturbative formulations."
---

## Summary

Loop diagrams integrate over momenta that are not fixed by the external process. The dangerous ultraviolet region is the region where some internal momentum is much larger than every external momentum and mass. In that region, the loop cannot resolve the long-distance structure of the process. Its dependence on external data can be expanded in powers of momenta and masses.

That expansion is the essential point:

$$
\text{hard loop momentum}
\quad\Longrightarrow\quad
\text{polynomial in external momenta}
\quad\Longrightarrow\quad
\text{local operators in position space}.
$$

This is why counterterms are local. A high-momentum subgraph may be divergent, but its divergent part is not arbitrary nonlocal chaos. Locality of the original theory forces the ultraviolet ambiguity to have the form of local terms already compatible with the symmetries.

<figure class="doc-figure" style="--figure-width: 43rem; --caption-width: 55rem;">

![A high-momentum one-loop subgraph shrinks to a local operator expansion](/figures/renormalization-rg-eft/loop-shrinks-to-counterterm.svg)

<figcaption>

The ultraviolet part of a loop subgraph is insensitive to the detailed long-distance arrangement of external legs. Expanding in external momenta turns the hard subgraph into local operators such as $\mathcal O$, $\partial^2\mathcal O$, and higher-derivative terms.

</figcaption>
</figure>

:::note[The locality theorem hiding in perturbation theory]
Power-counting tells you which diagrams might diverge. Locality tells you what shape the divergence can have. Without locality, renormalization would be a miracle. With locality, counterterms are exactly the terms you should have expected.
:::

## Prerequisites

You should have read [Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/). You should know that position-space coincident-point singularities and momentum-space ultraviolet divergences are the same phenomenon in different representations.

You do not need full loop-integration technology. We will use only one idea from asymptotic analysis: when $|\ell|\gg |p|,m$, an integrand can be expanded in small ratios such as $p/\ell$ and $m/\ell$.

## Core idea

A loop integral usually has several momentum regions. Some regions are physical and nonlocal: thresholds, branch cuts, long-distance propagation, and infrared sensitivity. The ultraviolet region is different. There, internal lines carry momenta much larger than the external momenta. The subgraph becomes small in position space.

A small subgraph looks pointlike to long-wavelength probes. Therefore its ultraviolet contribution must be expressible as a sum of local interactions:

$$
\int d^d x\, c_0\mathcal O(x)
+\int d^d x\, c_2\partial^2\mathcal O(x)
+\int d^d x\, c_4\partial^4\mathcal O(x)+\cdots.
$$

The coefficients $c_i$ may be divergent, regulator-dependent, and scheme-dependent. The operators $\mathcal O,\partial^2\mathcal O,\ldots$ are local. That is the crucial separation.

Counterterms subtract the regulator-dependent local coefficients. The nonlocal pieces, such as logarithms with physical branch cuts, remain and carry physical information.

## Setup and conventions

We use mostly-minus Lorentzian conventions in the rest of the volume, but many power-counting examples are easiest after Wick rotation. In Euclidean notation, a scalar one-loop bubble with external momentum $p$ has the schematic form

$$
I(p)=\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}.
$$

The same logic applies to Lorentzian integrals after the usual $i\epsilon$ prescription and Wick-rotation care. We focus here on the ultraviolet region

$$
|\ell|\gg |p|,m.
$$

A regulator is assumed when needed. It could be a hard cutoff $\Lambda$, dimensional regularization, Pauli–Villars fields, a lattice spacing, or a smooth Wilsonian cutoff. Different regulators display the same locality in different notation.

## The hard-momentum expansion

In the hard region, expand the second propagator:

$$
\frac{1}{(\ell+p)^2+m^2}
=\frac{1}{\ell^2+m^2}
\frac{1}{1+\frac{2\ell\cdot p+p^2}{\ell^2+m^2}}.
$$

When $|\ell|\gg |p|$, the second factor has a geometric expansion:

$$
\frac{1}{1+X}=1-X+X^2-\cdots,
\qquad
X=\frac{2\ell\cdot p+p^2}{\ell^2+m^2}.
$$

Thus the integrand becomes a series in powers of external momenta:

$$
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}
=\frac{1}{(\ell^2+m^2)^2}
-\frac{2\ell\cdot p+p^2}{(\ell^2+m^2)^3}
+\cdots.
$$

After angular integration, odd powers of $\ell_\mu$ vanish in a rotationally invariant regulator. Even powers reduce to tensors made from the metric. For example,

$$
\int d^d\ell\,\ell_\mu\ell_\nu F(\ell^2)
=\frac{\delta_{\mu\nu}}{d}\int d^d\ell\,\ell^2F(\ell^2)
$$

in Euclidean signature. Therefore the hard part has the form

$$
I_{\text{hard}}(p)
=A_0(\Lambda,m)+A_2(\Lambda,m)p^2+A_4(\Lambda,m)(p^2)^2+\cdots,
$$

up to tensor structures in theories with spin, gauge fields, or multiple external momenta.

The coefficients $A_i$ may diverge as the regulator is removed. But the dependence on the external data is polynomial. A polynomial in momentum is local in position space.

## Polynomial means local

The Fourier transform of a polynomial in momentum is a derivative of a delta function. With the convention

$$
F(x)=\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot x}\widetilde F(p),
$$

we have

$$
1\quad\Longleftrightarrow\quad \delta^{(d)}(x),
$$

and

$$
p^2\quad\Longleftrightarrow\quad -\partial^2\delta^{(d)}(x).
$$

Therefore a UV contribution of the form

$$
A_0+A_2p^2+A_4(p^2)^2+\cdots
$$

corresponds in position space to

$$
A_0\delta^{(d)}(x)
-A_2\partial^2\delta^{(d)}(x)
+A_4(\partial^2)^2\delta^{(d)}(x)+\cdots.
$$

These terms have support only when points coincide. They are contact terms.

In a Lagrangian, the same statement becomes the derivative expansion:

$$
\mathcal L_{\text{local}}
= c_0\mathcal O
+c_2\partial^2\mathcal O
+c_4\partial^4\mathcal O+\cdots,
$$

where integrations by parts, equations of motion, and symmetries are used to choose a convenient operator basis.

This is the simplest reason local counterterms work. A UV divergence is a divergent coefficient multiplying a local operator.

## Position-space picture: collapsing subgraphs

The same argument has a position-space version. Consider two interaction vertices at positions $x$ and $y$. Short-distance singularities occur when

$$
r=x-y\to0.
$$

If the rest of the diagram varies slowly over the tiny separation $r$, expand the fields around one point:

$$
\phi(x)=\phi(y+r)
=\phi(y)+r^\mu\partial_\mu\phi(y)
+\frac12r^\mu r^\nu\partial_\mu\partial_\nu\phi(y)+\cdots.
$$

The singular dependence on $r$ is integrated over a small region. The result is a sum of local operators at $y$:

$$
\int d^d r\, C(r)\phi(y+r)\phi(y)
\sim
c_0\phi^2(y)+c_2\partial_\mu\phi\partial^\mu\phi(y)+\cdots.
$$

The coefficients $c_i$ contain the short-distance integrals. If those integrals diverge, the corresponding local operator needs a counterterm.

Thus a UV-divergent subgraph is a small object being seen from far away. From far away, only its multipole expansion is visible. In QFT language, that multipole expansion is an expansion in local operators.

## A simple phi-four example

In four-dimensional scalar theory,

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

the one-loop correction to the four-point function contains the scalar bubble. In Euclidean notation, one channel has the form

$$
\mathcal A^{(1)}(p)
\propto \lambda^2
\int\frac{d^4\ell}{(2\pi)^4}
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}.
$$

At large $\ell$,

$$
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}
\sim \frac{1}{\ell^4}+O\!\left(\frac{p}{\ell^5},\frac{m^2}{\ell^6},\frac{p^2}{\ell^6}\right).
$$

The leading term gives

$$
\int^{\Lambda}\frac{d^4\ell}{(2\pi)^4}\frac{1}{\ell^4}
\sim \frac{1}{8\pi^2}\log\Lambda+\text{finite convention-dependent terms}.
$$

The divergent part is independent of $p$. It therefore has the same external-momentum dependence as the original $\phi^4$ vertex. The required counterterm is local:

$$
\mathcal L_{\text{ct}}\supset -\frac{\delta\lambda}{4!}\phi^4.
$$

This is not a lucky accident. It is the hard-momentum expansion in its simplest form.

At higher order in the expansion, terms proportional to $p^2$ correspond to higher-derivative local operators, such as schematically

$$
\phi^2\partial_\mu\phi\partial^\mu\phi,
\qquad
\phi^3\partial^2\phi,
$$

which can be related by integration by parts and equations of motion. In a renormalizable theory in four dimensions, these higher-derivative operators are often not needed to subtract divergences at a given order, but in an EFT they are expected and systematically included.

## Local divergent parts versus nonlocal finite parts

The full bubble integral is not only a polynomial. After evaluation, it contains nonlocal dependence on external momentum. In a massless or high-energy regime one often encounters terms of the form

$$
\log\frac{-p^2-i\epsilon}{\mu^2},
$$

or, with masses, threshold functions involving

$$
\sqrt{1-\frac{4m^2}{p^2}}
$$

and branch cuts. These terms are not local polynomials. They encode physical propagation over finite distances, thresholds for producing intermediate states, and unitarity cuts.

A local counterterm cannot remove a physical branch cut. Nor should it. Counterterms remove the regulator-dependent local ambiguity. The nonlocal finite remainder is part of the prediction.

This gives a useful diagnostic:

| Momentum dependence | Position-space meaning | Counterterm status |
|---|---|---|
| constant | $\delta(x)$ | local counterterm possible |
| polynomial in $p$ | derivatives of $\delta(x)$ | local counterterm possible |
| $\log(-p^2/\mu^2)$ | long-range distribution | not removable by a finite set of local counterterms |
| threshold branch cut | physical intermediate states | not a counterterm |
| inverse powers such as $1/p^2$ | massless long-distance propagation | infrared or physical exchange, not UV locality |

Renormalization does not delete the nonlocal parts of loop diagrams. It isolates them from the local regulator-dependent parts.

## Power counting and possible counterterms

Power counting estimates which local operators can receive divergent coefficients. Suppose a diagram has superficial degree of divergence $D$. Roughly, the UV part can generate a polynomial in external momenta of degree at most $D$:

$$
\mathcal A_{\text{UV}}(p_i)
=\sum_{n=0}^{D} C_n(\Lambda)\,P_n(p_i,m)
$$

when $D\ge0$, where $P_n$ is a local polynomial of degree $n$. If $D<0$, the diagram is superficially convergent, although subdivergences may still be present.

The phrase “superficial” matters. Symmetries can force cancellations. Gauge invariance can forbid mass terms. Chiral symmetry can forbid fermion masses. Equations of motion can move terms between operator bases. Subdivergences can appear inside an overall convergent graph.

Still, power counting gives the first map of what counterterms could be required:

$$
D\ge0
\quad\Longrightarrow\quad
\text{possible local UV counterterms of dimension allowed by }D.
$$

This is why a renormalizable theory has only finitely many counterterms of the same form as terms already present in the Lagrangian, while an EFT contains an infinite tower organized by increasing dimension.

## Subdivergences: locality inside locality

A multi-loop diagram can contain divergent subgraphs. The whole diagram may have one superficial degree of divergence, while a smaller part of it has another. Renormalization must subtract the small divergent pieces before or alongside the overall divergence.

The local picture remains the same. Each divergent subgraph shrinks to a local insertion. After that insertion is subtracted or replaced by a counterterm, the reduced graph may still have its own overall divergence, which is again local.

Schematic example:

$$
\text{large graph with divergent subgraph}
\longrightarrow
\text{graph with local counterterm insertion}
\longrightarrow
\text{remaining local overall subtraction if needed}.
$$

This nested structure is the intuitive content behind systematic renormalization algorithms such as BPHZ and the forest formula. The technical machinery can be formidable, but the picture is simple: every UV-divergent short-distance cluster is replaced by a local operator.

## Locality and symmetries

Locality says the divergent part is a local operator. Symmetry says which local operators are allowed.

For example, in a scalar theory with $\phi\to-\phi$, counterterms cannot contain odd powers such as $\phi$ or $\phi^3$. In a gauge theory, counterterms must respect gauge invariance or, after gauge fixing, the corresponding BRST/Slavnov–Taylor constraints. In a chiral theory, fermion mass terms may be forbidden. In an EFT, all symmetry-allowed operators appear unless there is a reason to exclude them.

This is why the counterterm problem is really two problems:

$$
\text{UV locality}
\quad+
\text{symmetry classification of local operators}.
$$

Once both are known, the rest is bookkeeping: compute coefficients, choose a subtraction scheme, and relate parameters to observables.

## Where locality does not mean simplicity

Locality of UV divergences is powerful, but it should not be overinterpreted.

First, massless theories can have infrared divergences. In dimensional regularization, UV and IR divergences can both appear as $1/\epsilon$ poles. A scaleless integral may vanish because a UV pole cancels an IR pole. That zero does not mean there was no physics; it means the regulator hid two opposite singularities in one line.

Second, anomalies are local but not always removable. An anomaly is often detected as a local term in a Ward identity. The question is whether a local counterterm can restore the symmetry while preserving all other required symmetries. Sometimes it cannot.

Third, gauge theories require symmetry-preserving organization. A naive cutoff may produce local terms that obscure gauge invariance. Dimensional regularization and background-field methods are popular partly because they make the symmetry constraints easier to preserve.

Fourth, Wilsonian locality can fail when massless fields are integrated out too aggressively. Integrating out heavy particles produces local EFT operators at energies $Q\ll M$. Integrating out massless particles usually produces nonlocal effects because massless propagation occurs over arbitrarily long distances.

The correct slogan is not “loops are local.” The correct slogan is:

$$
\text{the ultraviolet part of a loop subgraph in a local QFT is local.}
$$

That qualifier does a lot of work.

## Counterterms as local repairs

A counterterm is a local term added to the Lagrangian so that renormalized quantities remain finite and match chosen physical or scheme definitions. In the scalar example, one writes

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}},
$$

with

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4+\cdots.
$$

The dots are not moral failure. They are a reminder that the most general local theory contains every operator allowed by the symmetries. In a perturbatively renormalizable theory, only finitely many such terms are needed for UV divergences at a given renormalizable level. In an EFT, the infinite tower is organized by powers of $Q/M$.

The locality argument explains why this organization is possible. If UV divergences were arbitrary functions of external momenta, no finite or ordered set of local counterterms could control them. But because hard subgraphs expand in polynomials, local counterterms are the correct language.

## Common pitfalls

**Saying “the loop is local.”** The full loop is generally not local. Its ultraviolet part is local. The finite nonlocal part often contains the actual physics.

**Subtracting physical branch cuts.** A branch cut from an on-shell threshold is not a UV divergence. It is required by unitarity and should not be removed by a counterterm.

**Ignoring subdivergences.** A graph can be overall convergent but contain divergent subgraphs. Locality applies recursively to each UV-divergent subgraph.

**Trusting power counting too much.** Power counting identifies possible divergences, not guaranteed divergences. Symmetries and numerator cancellations can improve the behavior.

**Forgetting symmetry constraints.** Locality alone permits many terms. The actual counterterm basis is the set of local terms compatible with the symmetries and redundancies of the theory.

**Confusing Wilsonian and renormalized perturbative language.** In Wilsonian RG, integrating out hard modes actually changes the cutoff-dependent action. In renormalized perturbation theory, counterterms remove regulator dependence in a chosen scheme. The languages are related but not identical.

## Relations to other pages

[Short-Distance Singularities](/renormalization-rg-eft/why-renormalization/short-distance-singularities/) explained why coincident products of local fields are singular. This page explains why the ultraviolet part of those singularities is local.

Divergences as Local Operators will turn the locality argument into a classification principle: divergences are organized by the local operators allowed by the theory's symmetries. Bare Versus Renormalized will then explain how local coefficients are split into bare parameters, counterterms, and renormalized parameters.

For calculation details, compare the Perturbative QFT pages on loop expansion, superficial degree of divergence, dimensional regularization, one-loop bubble integrals, and counterterm insertions. For the deeper Wilsonian version, continue later to Wilsonian Effective Action and Integrating Out Modes.

## Research status

The locality of ultraviolet divergences in perturbative local QFT is established. It underlies standard renormalization proofs, counterterm classifications, effective field theory, and the Wilsonian viewpoint.

The active work is not about whether UV divergences are local, but about implementing the principle cleanly in increasingly sophisticated settings: gauge theories and BRST cohomology, chiral theories and anomalies, EFT operator bases, curved spacetime, boundaries and defects, nonlocal observables, overlapping UV/IR regions, and nonperturbative definitions.

## Exercises

### Exercise 1: Expand the hard region of the bubble

For

$$
I(p)=\int\frac{d^d\ell}{(2\pi)^d}
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)},
$$

expand the integrand through first order in $p$ in the region $|\ell|\gg |p|$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\frac{1}{(\ell+p)^2+m^2}
=\frac{1}{\ell^2+m^2}
\frac{1}{1+\frac{2\ell\cdot p+p^2}{\ell^2+m^2}}.
$$

Using $(1+X)^{-1}=1-X+O(X^2)$ gives

$$
\frac{1}{(\ell+p)^2+m^2}
=\frac{1}{\ell^2+m^2}
-\frac{2\ell\cdot p+p^2}{(\ell^2+m^2)^2}+O(p^2, p^3),
$$

where the notation is schematic because $p^2$ is second order while $\ell\cdot p$ is first order in $p$. Multiplying by the first propagator gives

$$
\frac{1}{(\ell^2+m^2)((\ell+p)^2+m^2)}
=\frac{1}{(\ell^2+m^2)^2}
-\frac{2\ell\cdot p+p^2}{(\ell^2+m^2)^3}+\cdots.
$$

The term linear in $\ell\cdot p$ vanishes after symmetric angular integration.

</details>

### Exercise 2: Polynomial momentum dependence is local

Show that a momentum-space term $A+Bp^2$ in a two-point function corresponds to contact terms in position space.

<details><summary><strong>Solution</strong></summary>

Using

$$
F(x)=\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot x}\widetilde F(p),
$$

the constant term gives

$$
\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot x}A
=A\delta^{(d)}(x).
$$

For $p^2$,

$$
\int\frac{d^d p}{(2\pi)^d}e^{ip\cdot x}p^2
=-\partial^2\delta^{(d)}(x),
$$

because $\partial^2e^{ip\cdot x}=-p^2e^{ip\cdot x}$ in Euclidean signature. Therefore

$$
A+Bp^2
\quad\Longleftrightarrow\quad
A\delta^{(d)}(x)-B\partial^2\delta^{(d)}(x).
$$

Both are local contact terms.

</details>

### Exercise 3: Why a logarithm is not a counterterm

Explain why a term proportional to $\log(p^2/\mu^2)$ cannot be removed by adding finitely many local counterterms.

<details><summary><strong>Solution</strong></summary>

A finite number of local counterterms gives a finite polynomial in momentum:

$$
P(p)=a_0+a_2p^2+a_4(p^2)^2+\cdots+a_{2N}(p^2)^N.
$$

The function $\log(p^2/\mu^2)$ is not a polynomial. It also has nonanalytic behavior at $p^2=0$ and, after Lorentzian continuation, branch cuts associated with physical thresholds or massless propagation. A finite local counterterm cannot reproduce or cancel such nonanalyticity. Local counterterms can change polynomial pieces and scale conventions, but the nonlocal logarithmic dependence remains part of the renormalized amplitude.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Renormalization and Symmetry,” “Dilatations,” and “Asymptotic Freedom.”
- Mark Srednicki, *Quantum Field Theory*, especially the sections on loop corrections, higher-order corrections, renormalizability, renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 16–23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for the general structure of perturbative renormalization and counterterms.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200, for the Wilsonian interpretation of short-distance modes and local effective actions.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for perturbative renormalization, locality, and the connection to statistical field theory.

## Version history

- 2026-06-16: First polished draft. Explained hard loop momentum, local momentum expansions, contact terms, subdivergences, symmetry constraints, and the distinction between local UV parts and nonlocal physical loop effects.
