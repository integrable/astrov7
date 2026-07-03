---
title: "Anomaly Matching"
description: "Explains ’t Hooft anomaly matching as the equality of UV and IR anomaly classes along symmetry-preserving RG flows, with mechanisms, examples, and checks."
sidebar:
  label: "Anomaly Matching"
  order: 2
level: Advanced
status: "Polished draft"
source: "’t Hooft anomaly matching; chiral symmetry in QCD-like theories; Wess–Zumino–Witten terms; anomaly inflow; Coleman–Grossman; Srednicki; Schwartz; Weinberg; modern generalized-symmetry viewpoint."
topics:
  - anomaly matching
  - thooft anomalies
  - RG invariance
  - chiral symmetry
  - Wess–Zumino–Witten terms
  - infrared constraints
  - symmetry breaking
canonicalTopics:
  - anomaly-matching
  - uv-ir-anomaly-invariance
  - thooft-consistency-condition
  - wess-zumino-witten-matching
  - anomaly-inflow
researchStatus:
  established:
    - "Along a symmetry-preserving RG flow, the ’t Hooft anomaly class of an exact global symmetry is invariant and must be reproduced by the infrared theory."
    - "A trivially gapped, unique, symmetry-preserving infrared phase cannot realize a nonzero ’t Hooft anomaly as a standalone theory."
  active:
    - "Modern anomaly matching includes higher-form, higher-group, discrete, fermionic, crystalline, non-invertible, and symmetry-TFT formulations, where matching can involve topological sectors or categorical symmetry data."
---

## Summary

**Anomaly matching** is the statement that ’t Hooft anomalies are invariant under RG flow. If a UV theory with exact global symmetry $G$ flows to an IR description that preserves the same symmetry, then

$$
\mathcal A_G^{\rm UV}=\mathcal A_G^{\rm IR}
$$

as anomaly classes.

This does not mean that the same fields must survive at low energy. It means that the same obstruction to gauging $G$ must be visible in the infrared. The IR can match the anomaly using massless fermions, Goldstone modes with a Wess–Zumino or Wess–Zumino–Witten term, topological order, protected boundary modes, a decoupled TQFT, or another nontrivial symmetry realization.

The sharp consequence is:

$$
\mathcal A_G\ne 0
\quad\Longrightarrow\quad
\text{no symmetric, trivially gapped, unique-vacuum IR phase}.
$$

That one line is the workhorse. It turns a UV one-loop calculation, or a topological background-field computation, into a nonperturbative constraint on phases and dualities.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing a UV theory coupled to the same background field as an IR theory along RG flow, with the anomaly class preserved and possible infrared matching mechanisms listed.](/figures/symmetry-anomalies-topology/anomaly-matching-rg-flow.svg)

<figcaption>

Anomaly matching compares theories in the same background fields. Massive modes may change local counterterms, but they cannot change the nontrivial anomaly class. The infrared must carry the same obstruction by some mechanism.

</figcaption>
</figure>

## Prerequisites

Read [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) first. You should also know [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

For the QCD example, it helps to know the basic idea of [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/) and Goldstone modes.

## Core idea

A ’t Hooft anomaly is not an ordinary local coupling that can run. It is obstruction data for coupling a global symmetry to backgrounds. Along an RG flow, high-energy modes can generate local background counterterms, but they cannot erase a nontrivial obstruction class.

The logic is:

1. couple the UV theory to background fields $A$ for the exact global symmetry $G$;
2. integrate out short-distance modes while keeping $A$ arbitrary;
3. compare the resulting long-distance generating functional with the proposed IR theory in the same $A$;
4. discard changes that are local counterterms;
5. demand that the anomaly classes agree.

The comparison is not a comparison of Lagrangians. It is a comparison of how the partition function transforms over the whole background-field space.

## Setup and conventions

Let $\mathcal T_{\rm UV}$ flow to $\mathcal T_{\rm IR}$ under RG. Assume the global symmetry $G$ is exact and is not explicitly broken along the flow. Couple both descriptions to the same class of background $G$ fields, written $A$.

We write the background-field generating functionals as

$$
Z_{\rm UV}[A]
\quad\text{and}\quad
Z_{\rm IR}[A].
$$

At scales much below the masses of fields that have been integrated out, locality implies a relation of the form

$$
Z_{\rm UV}[A]
\simeq
\exp\!\left(iS_{\rm local}[A]\right)Z_{\rm IR}[A]
$$

up to terms irrelevant at long distances. The local functional $S_{\rm local}[A]$ can include contact terms and topological response terms for the background fields. Its variation can change the **representative** of the anomaly, but not the anomaly class.

:::note[Convention-sensitive source note]
Some authors state anomaly matching using the anomalous divergence of currents, while others state it using effective actions, anomaly polynomials, or inflow. These are equivalent only after choosing the same background fields, current normalizations, counterterm scheme, and global form of the symmetry.
:::

## UV–IR matching statement

Suppose the UV partition function transforms under a background gauge transformation as

$$
Z_{\rm UV}[A^g]
=e^{2\pi i\mathcal A_g^{\rm UV}[A]}Z_{\rm UV}[A],
$$

and the IR partition function transforms as

$$
Z_{\rm IR}[A^g]
=e^{2\pi i\mathcal A_g^{\rm IR}[A]}Z_{\rm IR}[A].
$$

Using

$$
Z_{\rm UV}[A]
\simeq e^{iS_{\rm local}[A]}Z_{\rm IR}[A],
$$

we find

$$
\mathcal A_g^{\rm UV}[A]
=
\mathcal A_g^{\rm IR}[A]
+
\frac{1}{2\pi}\left(S_{\rm local}[A^g]-S_{\rm local}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

The last term is the shift produced by a local counterterm. Therefore the invariant statement is

$$
[\mathcal A_G^{\rm UV}]=[\mathcal A_G^{\rm IR}].
$$

For local perturbative anomalies, this can be expressed as equality of anomaly polynomials:

$$
I_{d+2}^{\rm UV}=I_{d+2}^{\rm IR}
$$

up to terms corresponding to local counterterm ambiguities and decoupled invertible sectors. For global, finite, torsion, spin, Pin, and higher-form anomalies, the correct object is generally not just a polynomial. One must match the full anomaly class.

## Why matching is powerful

The UV anomaly is often easy to compute. In a weakly coupled microscopic description, it may be a one-loop fermion triangle, a Fujikawa Jacobian, an index-theorem formula, or a characteristic-class computation.

The IR dynamics may be strongly coupled and hard. Anomaly matching bypasses the hard question by asking what the IR **must** do if the symmetry is preserved.

A nonzero anomaly rules out the most boring possible endpoint:

$$
\text{unique vacuum}
+
\text{mass gap}
+
\text{unbroken symmetry}
+
\text{no topological order}
\quad\Longrightarrow\quad
\mathcal A_G=0.
$$

So if $\mathcal A_G\ne0$, at least one assumption must fail.

The theory may:

| Matching mechanism | How the anomaly appears |
|---|---|
| Massless particles | Their current correlators or fermion measure reproduce the anomaly. |
| Spontaneous symmetry breaking | Goldstone modes carry Wess–Zumino or Wess–Zumino–Witten terms. |
| Topological order | A low-energy TQFT has anomalous symmetry action or boundary realization. |
| Boundary/edge modes | The anomaly is cancelled by inflow from a bulk or protected by an edge sector. |
| Symmetry extension or higher-group structure | The apparent symmetry action is refined in the IR. |
| Dual description | Different variables produce the same anomaly class. |

The anomaly does not tell you which mechanism occurs. It tells you which mechanisms are impossible and gives a stringent check on proposed ones.

## Sketch from background locality

The matching argument is one of those beautiful “nothing up my sleeve” arguments.

Start with the UV theory in a background $A$ and integrate out modes above a scale $\mu$. Since the background is nondynamical, it is not integrated out. The resulting effective description must still know how it transforms under background gauge transformations.

Massive modes can leave behind local terms in $A$ because, at distances much longer than their Compton wavelengths, their effects are local. Thus the low-energy effective functional has the form

$$
W_{\rm UV}[A]
=
W_{\rm IR}[A]+S_{\rm local}[A]+\cdots,
$$

where $Z=e^{iW}$ in Lorentzian signature and the ellipsis denotes irrelevant derivative corrections or massive-state effects.

Varying under a background gauge transformation gives

$$
\delta W_{\rm UV}[A]
=
\delta W_{\rm IR}[A]+
\delta S_{\rm local}[A]+\cdots.
$$

The local term is precisely the counterterm ambiguity. Therefore the nonlocal or cohomologically nontrivial obstruction agrees between UV and IR.

The inflow proof says the same thing more geometrically. If the anomaly is represented by a bulk invertible theory on $X_{d+1}$ with $\partial X_{d+1}=M_d$, then the boundary RG flow can change the boundary degrees of freedom but not the bulk topological response class. The anomaly attached to the boundary remains the same.

## QCD-like chiral symmetry example

The classic example is massless QCD with $N_c$ colors and $N_f$ massless Dirac quarks. Ignoring discrete quotients for a first pass, the continuous chiral flavor symmetry is

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_B.
$$

The UV degrees of freedom are quarks. They are weakly useful for computing flavor anomalies even though the IR dynamics is strongly coupled. The left-handed quarks contribute to $SU(N_f)_L^3$ anomalies with coefficient proportional to $N_c$, and the right-handed quarks contribute to $SU(N_f)_R^3$ anomalies with the opposite chirality sign. There are also mixed anomalies involving baryon number and flavor backgrounds.

If the IR were a unique, gapped, symmetry-preserving, topologically trivial vacuum, there would be no way to reproduce these chiral flavor anomalies. Therefore that IR scenario is ruled out.

The observed and theoretically expected solution is chiral symmetry breaking,

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V.
$$

The low-energy fields are Goldstone bosons packaged into

$$
U(x)\in SU(N_f).
$$

For $N_f\ge 3$, the Goldstone effective action includes a Wess–Zumino–Witten term whose coefficient is quantized and equal to $N_c$. Its anomalous variation in flavor backgrounds reproduces the UV quark anomaly.

This is anomaly matching in its most famous form:

$$
\text{quark triangle anomaly in the UV}
=
\text{Wess–Zumino–Witten variation in the IR}.
$$

:::note[Convention-sensitive source note]
The coefficient of the Wess–Zumino–Witten term depends on the normalization of the flavor generators and on the convention for treating right-handed fermions as left-handed conjugates. The invariant statement is that the WZW level matches the UV color multiplicity $N_c$, with signs fixed by the $L$ versus $R$ chirality convention.
:::

For $N_f=2$, the ordinary five-form WZW story has special features because $\pi_5(SU(2))$ differs from the $N_f\ge3$ case. Refined global anomalies and baryon-number backgrounds are then a better language. The moral is not that the $N_f=2$ theory escapes matching; it is that global anomaly data must be stated with the correct global symmetry and topology.

## Matching with unbroken symmetry

Anomaly matching does not require spontaneous symmetry breaking. Another possibility is that the IR contains massless composite fermions whose anomalies match the UV.

This is the logic behind many proposed chiral gauge theory phases and dualities. One proposes a set of massless IR fields, computes their global anomalies, and checks whether they reproduce the UV anomaly coefficients.

For continuous symmetries with Weyl fermions, the basic algebraic check is often:

$$
\operatorname{Tr}_{\rm UV}(T_a\{T_b,T_c\})
=
\operatorname{Tr}_{\rm IR}(T_a\{T_b,T_c\}),
$$

along with mixed gravitational and abelian anomaly coefficients such as

$$
\operatorname{Tr}_{\rm UV}(q)
=
\operatorname{Tr}_{\rm IR}(q),
\qquad
\operatorname{Tr}_{\rm UV}(q^3)
=
\operatorname{Tr}_{\rm IR}(q^3).
$$

These equations are necessary, not sufficient. Matching anomalies does not prove the proposed IR theory is correct. It only says that it passes one very hard consistency test.

## Matching with topological order

A gapped IR phase can match an anomaly if it is not trivial. In modern language, the IR may contain a TQFT with anomalous symmetry action. This is common in condensed matter, discrete gauge theories, and generalized-symmetry examples.

The schematic structure is

$$
Z_{\rm IR}[A]=Z_{\rm TQFT}[A],
$$

where $Z_{\rm TQFT}[A]$ is not a harmless constant. It depends on the background topology and transforms anomalously in exactly the way required by the UV anomaly.

This possibility is why the phrase “an anomaly forbids a gap” is too strong. The correct statement is:

$$
\text{a nonzero anomaly forbids a trivial symmetric gap}.
$$

A nontrivial symmetric gapped phase with topological order may be allowed.

## Matching and duality

Anomaly matching is a basic test of duality. If two theories are claimed to describe the same infrared fixed point, then their exact global symmetries and ’t Hooft anomalies must agree.

In supersymmetric dualities, anomaly matching can be astonishingly constraining because holomorphy, supersymmetry, and global symmetry determine many charges. In non-supersymmetric dualities, anomaly matching is often one of the first sanity checks before more dynamical evidence is considered.

The important caveat is that duality can hide symmetries. A symmetry manifest in one description may act nonlocally or emergently in another. Matching must be done for the true symmetry, including its global form, background fields, and possible higher-form sectors.

## How to use anomaly matching

A practical anomaly-matching calculation follows this workflow.

| Step | Task | Common failure mode |
|---:|---|---|
| 1 | Identify the exact global symmetry $G$. | Including a symmetry broken by an anomaly or missing a quotient. |
| 2 | Decide what backgrounds are allowed. | Using only Lie algebra data and missing global-form constraints. |
| 3 | Compute the UV anomaly. | Forgetting signs of right-handed fermions or mixed anomalies. |
| 4 | Propose an IR realization. | Assuming the same microscopic fields must appear. |
| 5 | Compute the IR anomaly. | Forgetting Wess–Zumino terms, TQFT sectors, or edge modes. |
| 6 | Compare classes, not formulas. | Mistaking a counterterm shift for a mismatch. |

A mismatch means at least one of the assumptions is wrong: the proposed IR phase is incomplete, the symmetry was misidentified, a topological sector was omitted, a counterterm convention differs, or the claimed duality is false.

## Common pitfalls

**Matching fields instead of anomalies.** The IR does not need to contain the UV fermions. It only needs to reproduce the same background-field obstruction.

**Using the wrong symmetry.** The exact global symmetry may be a quotient, a discrete remnant, a higher group, or a symmetry mixed with fermion parity. Matching the anomaly of the wrong group is not meaningful.

**Forgetting symmetry breaking.** When a symmetry is spontaneously broken, the IR Goldstone theory can still match the UV anomaly through Wess–Zumino terms. A nonzero anomaly does not imply the symmetry is unbroken.

**Saying “anomaly means gapless.”** A nonzero anomaly forbids a trivial symmetric gapped phase, not every gapped phase. Topological order can match anomalies.

**Comparing representatives instead of classes.** Two formulas may differ by a local counterterm and still represent the same anomaly. Conversely, two formulas that look similar locally may differ by global torsion data.

## Relations to other pages

- [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) defines the anomaly class that this page matches.
- [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/) explains the symmetry-breaking mechanism used in the QCD-like example.
- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) explains the consistency condition satisfied by local anomaly representatives.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) give the local perturbative machinery for computing anomaly representatives.
- [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) explains anomalies invisible to infinitesimal triangle coefficients but still subject to matching.

## Research status

The basic ’t Hooft anomaly matching principle is established and is one of the standard nonperturbative tools of QFT. Its classic use in QCD-like theories, chiral symmetry breaking, Wess–Zumino–Witten terms, and duality checks is settled at the level of theoretical framework.

The active research frontier is the range of objects that can carry anomaly data. Modern matching can involve higher-form symmetries, higher groups, non-invertible symmetries, categorical defects, crystalline symmetries, fermionic invertible phases, subsystem symmetries, and relative QFTs. The slogan “UV anomaly equals IR anomaly” remains the guide, but the mathematical object represented by the word “anomaly” can be more refined than a polynomial or a triangle diagram.

## Exercises

### Exercise 1: Derive matching modulo counterterms

Assume

$$
Z_{\rm UV}[A]=e^{iS_{\rm local}[A]}Z_{\rm IR}[A].
$$

If $Z_{\rm UV}$ and $Z_{\rm IR}$ transform with anomaly phases $\mathcal A_g^{\rm UV}$ and $\mathcal A_g^{\rm IR}$, show that the two differ only by a counterterm shift.

<details>
<summary><strong>Solution</strong></summary>

Apply the transformation to both sides:

$$
Z_{\rm UV}[A^g]
=e^{iS_{\rm local}[A^g]}Z_{\rm IR}[A^g].
$$

Using the anomaly transformations,

$$
e^{2\pi i\mathcal A_g^{\rm UV}[A]}Z_{\rm UV}[A]
=e^{iS_{\rm local}[A^g]}e^{2\pi i\mathcal A_g^{\rm IR}[A]}Z_{\rm IR}[A].
$$

Substitute $Z_{\rm UV}[A]=e^{iS_{\rm local}[A]}Z_{\rm IR}[A]$ and cancel $Z_{\rm IR}[A]$. Then

$$
2\pi\mathcal A_g^{\rm UV}[A]+S_{\rm local}[A]
=
S_{\rm local}[A^g]+2\pi\mathcal A_g^{\rm IR}[A]
\quad \mathrm{mod}\;2\pi.
$$

Thus

$$
\mathcal A_g^{\rm UV}[A]
=
\mathcal A_g^{\rm IR}[A]
+
\frac{1}{2\pi}\left(S_{\rm local}[A^g]-S_{\rm local}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

The difference is exactly a local counterterm shift.

</details>

### Exercise 2: Why a trivial symmetric gap is impossible

Explain why a nonzero ’t Hooft anomaly forbids an infrared phase with a unique gapped vacuum, unbroken symmetry, and no topological order.

<details>
<summary><strong>Solution</strong></summary>

A unique gapped phase with unbroken symmetry and no topological order has no long-distance degrees of freedom that can transform anomalously. Its low-energy partition function in background fields is, at most, a local background response that can be regarded as a counterterm or invertible response within the $d$-dimensional theory.

Such local terms can change anomaly representatives but cannot produce a nontrivial obstruction to gauging. Therefore the anomaly class of a trivially gapped symmetric standalone IR theory is zero. If the UV anomaly is nonzero, this phase cannot be the full infrared description.

</details>

### Exercise 3: QCD chiral anomaly matching

In massless QCD with $N_c$ colors and $N_f\ge3$ light flavors, why is it plausible that the Wess–Zumino–Witten term in the pion effective action has coefficient $N_c$?

<details>
<summary><strong>Solution</strong></summary>

In the UV, the chiral flavor anomaly is computed by quark loops. Each color gives one copy of the flavor representation, so the $SU(N_f)_L^3$ and $SU(N_f)_R^3$ anomaly coefficients are proportional to $N_c$, with opposite chirality signs for $L$ and $R$.

In the IR with chiral symmetry breaking, the degrees of freedom are pions valued in $SU(N_f)$. The Wess–Zumino–Witten term is the term in the Goldstone action whose background-gauge variation can reproduce the chiral anomaly. Therefore its quantized coefficient must be $N_c$ to match the UV anomaly.

</details>

### Exercise 4: Necessary but not sufficient

Why does matching all known ’t Hooft anomalies not prove that a proposed duality is true?

<details>
<summary><strong>Solution</strong></summary>

Anomaly matching tests only the response to background fields for exact symmetries. Two different theories can share the same anomalies but differ in spectra, operator dimensions, correlation functions, phases, or dynamics.

Therefore anomaly matching is a necessary condition for a duality or proposed IR phase, not a sufficient one. A mismatch is decisive evidence against a proposal, but a match is only one consistency check among many.

</details>

## References

### Standard first pass

- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30. Includes anomaly matching after triangle and path-integral anomaly derivations.
- M. Srednicki, *Quantum Field Theory*, §§75–77 and §83. Anomalies and chiral symmetry breaking in QCD-like theories.
- S. Coleman, *Aspects of Symmetry*, especially **Soft Pions**, **Secret Symmetry**, and **The Uses of Instantons**.

### Deeper references

- G. ’t Hooft, **Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking**, in *Recent Developments in Gauge Theories*, Cargèse 1979. The original anomaly-matching viewpoint.
- S. Coleman and B. Grossman, **’t Hooft’s Consistency Condition as a Consequence of Analyticity and Unitarity**, *Nuclear Physics B* 203 (1982). A classic analysis of the matching condition.
- E. Witten, **Global Aspects of Current Algebra**, *Nuclear Physics B* 223 (1983). The Wess–Zumino–Witten term and global aspects of current algebra.
- C. G. Callan and J. A. Harvey, **Anomalies and Fermion Zero Modes on Strings and Domain Walls**, *Nuclear Physics B* 250 (1985). Anomaly inflow and boundary matching.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, **Generalized Global Symmetries**, arXiv:1412.5148. Generalized symmetries, background fields, gauging, and anomaly matching.

## Version history

- **2026-06-18:** Initial polished draft. Added UV–IR matching statement, background-locality proof, QCD chiral-symmetry example, matching mechanisms, duality checks, pitfalls, and exercises.
