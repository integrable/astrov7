---
title: "WZW Term from Anomaly Inflow"
description: "A model calculation deriving the Wess–Zumino–Witten term as the infrared remnant of a UV chiral anomaly."
sidebar:
  label: "WZW Term from Inflow"
  order: 15
level: Advanced
status: "Polished draft"
source: "Witten 1983; Wess–Zumino 1971; Srednicki §§75–77, 83; Coleman, Soft Pions and Secret Symmetry; Alvarez-Gaumé–Witten 1984."
topics:
  - Wess–Zumino–Witten term
  - anomaly inflow
  - chiral symmetry
  - Goldstone bosons
  - anomaly matching
  - descent equations
canonicalTopics:
  - wzw-term
  - anomaly-inflow
  - chiral-anomaly
  - anomaly-matching
researchStatus:
  established:
    - "The Wess–Zumino–Witten term is the standard low-energy term that reproduces the chiral anomaly of a UV theory with Goldstone fields."
    - "Its coefficient is quantized by global topology and is fixed in QCD-like theories by anomaly matching."
  active:
    - "Generalized WZW terms for higher-form, non-invertible, fermionic, and symmetry-TFT settings remain active language-building territory."
---

## Summary

The Wess–Zumino–Witten term is the topological term in a Goldstone effective field theory that remembers an anomaly of the ultraviolet theory.

The simplest important example is QCD with $N_f$ light quark flavors. Ignoring quark masses, the classical flavor symmetry is approximately

$$
G_L\times G_R=SU(N_f)_L\times SU(N_f)_R,
$$

spontaneously broken to the diagonal subgroup

$$
G_V=SU(N_f)_V.
$$

The pion field is a map

$$
U:M_4\to SU(N_f),
$$

with transformation

$$
U\mapsto g_L U g_R^{-1}.
$$

The low-energy pion Lagrangian can reproduce ordinary symmetry breaking, but it cannot reproduce the chiral anomaly unless it contains an additional topological term. That term is the Wess–Zumino–Witten term,

$$
\Gamma_{\rm WZ}[U]
=
\frac{k}{240\pi^2}\int_{B_5}\omega_5(U),
\qquad
\partial B_5=M_4,
$$

where

$$
\omega_5(U)=-i\,\operatorname{tr}\left(U^{-1}dU\right)^5
$$

in the Hermitian-generator convention, and $k$ is an integer. For QCD with $N_c$ colors,

$$
k=N_c.
$$

The conceptual derivation is anomaly inflow: a five-dimensional topological term has a boundary variation, and that boundary variation is exactly the anomalous variation required of the four-dimensional Goldstone theory.

<figure class="doc-figure" style="--figure-width: 44rem;">

![The Wess–Zumino–Witten term as a five-dimensional inflow functional whose boundary variation reproduces a four-dimensional chiral anomaly.](/figures/symmetry-anomalies-topology/wzw-term-inflow-descent.svg)

<figcaption>

The WZW term is naturally written by extending the Goldstone field $U$ from spacetime $M_4$ to a five-manifold $B_5$ with $\partial B_5=M_4$. The dependence on the extension is invisible in the quantum phase precisely when the coefficient is quantized.

</figcaption>
</figure>

## Prerequisites

You should know the model-library pages on the ABJ anomaly and the Fujikawa Jacobian. You should also be comfortable with spontaneous chiral symmetry breaking, differential forms, and the idea that an anomaly is a controlled failure of background gauge invariance.

The notation here follows the volume convention of Hermitian generators. The trace $\operatorname{tr}$ is in the fundamental representation unless stated otherwise. The page is written in a compact differential-form notation because the WZW term is almost unreadable in components.

## Setup

Consider a four-dimensional theory with a global symmetry $G_L\times G_R$ that is spontaneously broken to $G_V$. The Goldstone field is a map

$$
U(x)\in G,
$$

where $G=SU(N_f)$ in the main example. It transforms as

$$
U(x)\mapsto g_L U(x)g_R^{-1}.
$$

A two-derivative sigma-model action begins as

$$
S_2=\frac{f_\pi^2}{4}\int_{M_4}d^4x\,
\operatorname{tr}\left(\partial_\mu U^\dagger\partial^\mu U\right).
$$

This term is invariant under $G_L\times G_R$, but it is too ordinary. It knows about the coset geometry and the Goldstone bosons; it does not know about the UV chiral anomaly.

To test the anomaly, couple the UV theory to nondynamical background fields $A_L$ and $A_R$ for $G_L$ and $G_R$. The fermion determinant is not invariant under independent background gauge transformations. In descent notation,

$$
I_6=dI_5,
\qquad
\delta_\lambda I_5=dI_4^{(1)}(\lambda,A),
$$

and the anomalous variation of the generating functional takes the schematic form

$$
\delta_\lambda W[A]=2\pi\int_{M_4} I_4^{(1)}(\lambda,A).
$$

The infrared theory must reproduce this same variation. This is anomaly matching.

:::note[Source note: descent normalization]
The precise factors of $2\pi$, $i$, and trace normalization depend on whether one writes anti-Hermitian mathematical connections or Hermitian particle-physics gauge fields. This page fixes the ungauged WZW normalization by the statement that changing the extension $B_5$ shifts $\Gamma_{\rm WZ}$ by $2\pi k\mathbb Z$.
:::

## The five-dimensional term

For $U:M_4\to SU(N_f)$, choose a five-dimensional manifold $B_5$ with boundary $M_4$ and extend $U$ to

$$
\widetilde U:B_5\to SU(N_f).
$$

Then define

$$
\Gamma_{\rm WZ}[U]
=
\frac{k}{240\pi^2}
\int_{B_5}
\omega_5(\widetilde U),
$$

where

$$
\omega_5(\widetilde U)
=
-i\,\operatorname{tr}
\left(\widetilde U^{-1}d\widetilde U\right)^5.
$$

The physical path integral contains

$$
\exp\left(i\Gamma_{\rm WZ}[U]\right).
$$

This expression looks suspicious: it uses a five-dimensional extension of a four-dimensional field. The rescue is topology. If two extensions $\widetilde U_1$ and $\widetilde U_2$ are chosen, gluing $B_5$ and $-B_5$ gives a closed five-manifold. The difference is an integral over a closed five-cycle. For $SU(N_f)$ with $N_f\ge 3$,

$$
\pi_5(SU(N_f))\cong\mathbb Z.
$$

With the normalization above, the difference is

$$
\Gamma_{\rm WZ}[\widetilde U_1]-\Gamma_{\rm WZ}[\widetilde U_2]
=
2\pi k n,
\qquad
n\in\mathbb Z.
$$

Therefore the phase $\exp(i\Gamma_{\rm WZ})$ is independent of the extension if

$$
k\in\mathbb Z.
$$

This is the first major lesson: the coefficient of the WZW term is quantized.

## Why the coefficient is fixed

Topology says $k$ must be an integer. Physics says which integer.

In QCD-like theories, the UV fermions carry color and flavor. The color index is a multiplicity for the flavor anomaly. Each color contributes one copy of the chiral flavor anomaly, so the coefficient of the Goldstone WZW term is

$$
k=N_c.
$$

This is not an adjustable coupling in the chiral Lagrangian. It is fixed by anomaly matching.

A good way to say this is:

$$
\text{UV chiral anomaly}
\quad\Longrightarrow\quad
\text{IR WZW coefficient}.
$$

The ordinary two-derivative pion action contains parameters such as $f_\pi$ that depend on dynamics. The WZW coefficient is different. It is a topological/anomalous datum inherited from the UV theory.

## How inflow produces the term

The WZW term can be understood as a transgression between two background gauge-field configurations.

Let $I_5(A)$ be a Chern–Simons form satisfying

$$
dI_5(A)=I_6(F).
$$

Under a background gauge transformation,

$$
\delta_\lambda I_5(A)=dI_4^{(1)}(\lambda,A).
$$

If a Goldstone field $U$ relates two background configurations, then the difference between the two Chern–Simons forms is not generally zero. Schematically,

$$
I_5(A^U)-I_5(A)
=
d(\cdots)+\text{Goldstone five-form}.
$$

The Goldstone five-form is the WZW term. Its boundary variation reproduces the anomaly.

This is the second major lesson: the WZW term is not guessed. It is forced by the same descent data that gives the anomaly.

## The ungauged versus gauged WZW term

The compact expression

$$
\frac{k}{240\pi^2}\int_{B_5}\omega_5(U)
$$

is the **ungauged** WZW term. It is enough to reveal the topological quantization and the anomaly-matching logic.

If background fields $A_L$ and $A_R$ are turned on, the full **gauged** WZW functional contains additional four-dimensional terms involving $U$, $A_L$, $A_R$, and their curvatures. These terms are not optional decorations. They are required so that the total variation is exactly the UV consistent anomaly.

Symbolically,

$$
\Gamma_{\rm gWZW}[U,A_L,A_R]
=
\Gamma_{\rm WZ}[U]
+
\int_{M_4}\Omega_4(U,A_L,A_R).
$$

The four-dimensional form $\Omega_4$ is convention-heavy. It depends on trace normalizations and on whether one chooses the consistent or covariant anomaly representative. The invariant statement is cleaner:

$$
\delta\Gamma_{\rm gWZW}
=
\delta W_{\rm UV}[A_L,A_R].
$$

That equation is the definition of doing it right.

## Physical consequence: pion decay to photons

One famous payoff is the neutral pion decay

$$
\pi^0\to\gamma\gamma.
$$

The WZW term contains the interaction responsible for this process. In a two-flavor truncation, the anomaly fixes the coefficient of the effective coupling

$$
\pi^0 F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The detailed electromagnetic embedding depends on the quark charge matrix, but the moral is robust: a process involving low-energy pions remembers a UV triangle anomaly.

This is one of the best physical examples of anomaly matching. The low-energy theory has no quarks as propagating fields, but it still knows their anomalous flavor current algebra through the WZW term.

## Relation to ordinary Wess–Zumino terms

A Wess–Zumino term is a term whose variation is local even if the term itself is most naturally written using one higher dimension. The WZW term is the Wess–Zumino term for a chiral sigma model, with a special quantization and current-algebra interpretation.

The name “Wess–Zumino–Witten” usually signals the full structure:

1. a local anomalous variation fixed by Wess–Zumino consistency;
2. a five-dimensional extension formula;
3. a quantized coefficient;
4. a connection to current algebra and anomaly matching;
5. in two-dimensional CFT, a closely related WZW model with affine current symmetry.

This page concerns the four-dimensional chiral Lagrangian WZW term. The two-dimensional WZW model belongs mainly to the low-dimensional symmetry and CFT chapters.

## Common pitfalls

**Thinking the WZW coefficient is a tunable EFT parameter.** It is quantized and anomaly-matched. In QCD-like theories it is fixed by $N_c$.

**Forgetting the extension-independence test.** The five-dimensional formula is meaningful only because the path-integral phase is independent of the chosen extension.

**Confusing the ungauged and gauged terms.** The five-form alone is not the full background-field answer. Background fields require additional four-dimensional terms.

**Comparing signs without checking conventions.** The WZW term is highly sensitive to Hermitian versus anti-Hermitian connections, Euclidean versus Lorentzian action conventions, and the orientation of $B_5$.

**Assuming all cosets have the same WZW term.** The existence and quantization of Wess–Zumino terms depend on topology and on the anomaly to be matched.

## Relations to other pages

This calculation connects the ABJ anomaly triangle, the Fujikawa Jacobian, the Wess–Zumino consistency condition, anomaly inflow, and chiral symmetry breaking. It is also a concrete bridge from the model-calculation library to the pages on SPT phases and anomalies, topological terms, and low-dimensional WZW/current-algebra technology.

In the broader volume, the WZW term is a prototype for a recurring pattern:

$$
\text{UV anomaly}
\quad\leadsto\quad
\text{IR topological term}
\quad\leadsto\quad
\text{boundary or defect inflow}.
$$

## Research status

The WZW term in chiral Lagrangians is established textbook physics. The coefficient quantization and anomaly-matching interpretation are standard.

Active generalizations include WZW-like terms for generalized symmetries, fermionic symmetry-protected phases, non-invertible symmetry defects, higher-group backgrounds, and symmetry TFT. In those settings the one-higher-dimensional viewpoint remains the guide, but the mathematical language may involve differential cohomology, bordism, higher categories, or defect-network state sums.

## Exercises

### Exercise 1: Why $N_f\ge 3$ matters

Explain why the standard $SU(N_f)$ five-dimensional WZW term requires nontrivial $\pi_5(SU(N_f))$.

<details><summary><strong>Solution</strong></summary>

The WZW term is written as an integral over a five-dimensional extension. Two different extensions differ by a map from a closed five-manifold into the target group. For the standard chiral term, the relevant winding is measured by

$$
\pi_5(SU(N_f)).
$$

For $N_f\ge3$,

$$
\pi_5(SU(N_f))\cong\mathbb Z,
$$

so the five-form has quantized periods and a quantized coefficient. When the relevant homotopy group is absent or torsion-valued, the form of possible topological terms changes.

</details>

### Exercise 2: Quantized coefficient

Suppose changing the extension shifts

$$
\int_{B_5}\frac{1}{240\pi^2}\omega_5(U)
$$

by $2\pi n$. Show that $\exp(i\Gamma_{\rm WZ})$ is extension-independent only if $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

The change in the WZW action is

$$
\Delta\Gamma_{\rm WZ}=2\pi k n.
$$

The path-integral phase changes by

$$
\exp(i\Delta\Gamma_{\rm WZ})
=
\exp(2\pi i k n).
$$

This equals $1$ for all $n\in\mathbb Z$ precisely when $k$ is an integer.

</details>

### Exercise 3: Anomaly matching logic

Why can the pion effective theory not simply omit the WZW term if the UV theory has a chiral anomaly?

<details><summary><strong>Solution</strong></summary>

A ’t Hooft anomaly is invariant under RG flow. If the UV theory has a chiral flavor anomaly, the IR theory must reproduce the same anomalous variation under background flavor gauge transformations. The ordinary two-derivative pion action is invariant and therefore cannot supply that variation. The WZW term is the required IR term whose variation matches the UV anomaly.

</details>

### Exercise 4: Background fields

What changes when background fields $A_L$ and $A_R$ are turned on?

<details><summary><strong>Solution</strong></summary>

The ungauged five-dimensional WZW term is no longer the full answer. One must add four-dimensional terms involving $U$, $A_L$, $A_R$, and their curvatures. These terms form the gauged WZW functional. They are chosen so that the total anomalous variation equals the UV consistent anomaly:

$$
\delta\Gamma_{\rm gWZW}[U,A_L,A_R]
=
\delta W_{\rm UV}[A_L,A_R].
$$

</details>

## References

- J. Wess and B. Zumino, “Consequences of anomalous Ward identities,” *Physics Letters B* **37** (1971).
- E. Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* **223** (1983).
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* **234** (1984).
- S. Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “Secret Symmetry.”
- M. Srednicki, *Quantum Field Theory*, §§75–77 and §§83–94.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8 for Wess–Zumino and Chern–Simons terms in condensed-matter field theory.

## Version history

- 2026-06-23: Initial polished draft. Added five-dimensional WZW normalization, anomaly-inflow derivation, coefficient quantization, gauged-WZW caveats, pion-decay interpretation, exercises, and convention-sensitive source notes.
