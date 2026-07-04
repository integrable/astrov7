---
title: "Roadmap and References"
description: "A reading strategy for Modern CFT for AdS/CFT: what to learn, what to skip on a first pass, which references to use, and how the course prepares the holographic dictionary."
sidebar:
  order: 4
---

## The point of this page

This page explains how to use the course. A modern CFT course designed for AdS/CFT has a different center of gravity from a classic two-dimensional CFT course. The goal is not merely to learn many beautiful conformal tricks. The goal is to become fluent in the exact kind of CFT language that holography uses.

That language is built from a small number of recurring objects:

$$
\boxed{
\mathcal O_i,
\qquad
\Delta_i,
\qquad
\ell_i,
\qquad
C_{ijk},
\qquad
\langle \mathcal O_1\cdots \mathcal O_n\rangle,
\qquad
T_{\mu\nu},
\qquad
J_\mu.
}
$$

AdS/CFT turns these CFT objects into bulk objects. Operator dimensions become bulk masses. Conserved currents become bulk gauge fields. The stress tensor becomes the graviton. Large-$N$ factorization becomes weak bulk coupling. Sparse low-dimension single-trace spectra become approximate bulk locality. Thermal CFT states become black holes. Entanglement becomes geometry.

So the organizing principle of the course is:

$$
\boxed{
\text{learn CFT data in exactly the form in which it becomes bulk physics.}
}
$$

This page gives the roadmap, the reading strategy, the reference hierarchy, and a way to know whether you are ready to move from CFT to AdS/CFT.

<figure class="doc-figure" style="--figure-width: 60rem; --caption-width: 56rem;">

![Roadmap and reference paths for the course Modern CFT for AdS/CFT](/figures/cft/cft-roadmap-reference-paths.svg)

<figcaption>

The main path runs from QFT data and RG fixed points to conformal symmetry, Ward identities, correlators, OPE data, large-$N$ factorization, $\mathcal N=4$ SYM, and the AdS/CFT dictionary. The dashed paths are specialized but important: exact $d=2$ CFT technology feeds into string worldsheets and AdS$_3$/CFT$_2$, while Lorentzian, thermal, and entanglement diagnostics feed into black holes, causality, and holographic geometry.

</figcaption>
</figure>

## What counts as being ready for AdS/CFT?

A student is ready to begin AdS/CFT seriously when the following five fluencies feel natural.

First, one must understand CFT as a theory of local operators rather than primarily as a Lagrangian. A Lagrangian is useful when it exists, but the invariant data of a CFT are the spectrum and the OPE coefficients:

$$
\text{CFT data}
=
\left\{
\Delta_i,
\ell_i,
\mathcal R_i,
C_{ijk}
\right\}.
$$

Here $\Delta_i$ is the scaling dimension, $\ell_i$ is the spin, $\mathcal R_i$ denotes possible global-symmetry or $R$-symmetry representation labels, and $C_{ijk}$ are the three-point or OPE coefficients. Holography is most sharply formulated in this operator language.

Second, one must be comfortable with the stress tensor and Ward identities. The stress tensor is not just another operator. It is the operator that knows spacetime symmetry. In the holographic dictionary,

$$
T_{\mu\nu}
\longleftrightarrow
\text{bulk metric }g_{MN},
$$

so any confusion about $T_{\mu\nu}$ becomes confusion about gravity.

Third, one must know how conformal symmetry fixes two- and three-point functions and reduces four-point functions to functions of cross-ratios. The four-point function is where dynamics begins:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=\text{kinematic prefactor}\times \mathcal G(u,v).
$$

The function $\mathcal G(u,v)$ is the first place where the full operator algebra shows its teeth.

Fourth, one must know the OPE and conformal blocks well enough to recognize the bootstrap equation as associativity:

$$
(\mathcal O_1\mathcal O_2)\mathcal O_3
=
\mathcal O_1(\mathcal O_2\mathcal O_3).
$$

This is not merely a numerical-bootstrap slogan. In holography, different OPE channels become different bulk exchange channels. A conformal block is the CFT shadow of exchanging a conformal family; a Witten diagram is the bulk way to organize the same data in a large-$N$ expansion.

Fifth, one must understand large-$N$ CFTs. AdS/CFT is not a duality between an arbitrary CFT and a weakly curved classical bulk. Weakly coupled Einstein-like bulk physics requires special CFT structure: factorization, single-trace operators, multi-trace towers, a large gap to higher-spin single-trace operators, and suitable stress-tensor normalization.

The slogan is:

$$
\boxed{
\text{ordinary CFT} + \text{large }N + \text{sparse single-trace spectrum}
\approx
\text{local semiclassical AdS physics}.
}
$$

The purpose of this course is to build toward this sentence without hiding any of its words.

## The fourteen-module structure

The course is divided into fourteen modules. The first thirteen are the main lecture sequence; the last is a toolbox.

| Module | Main topic | What it teaches | Exit test |
|---:|---|---|---|
| 1 | Orientation | What CFT is for in AdS/CFT, what the observables are, and how Euclidean and Lorentzian languages fit together. | You can explain why AdS/CFT is a statement about sources and correlators, not only about matching symmetries. |
| 2 | RG fixed points | Wilsonian RG, fixed points, critical phenomena, trace of the stress tensor, and CFT data. | You can explain why $T^\mu{}_{\mu}=0$ is the local expression of conformality, up to beta functions, anomalies, and improvement subtleties. |
| 3 | Conformal geometry | Conformal transformations, $SO(d,2)$, compactification, cylinder, and embedding space. | You can derive the conformal algebra and see why it matches AdS isometries. |
| 4 | Operators, sources, and Ward identities | Primaries, descendants, currents, stress tensor, sources, generating functionals, and Ward identities. | You can read $Z_{\rm CFT}[J]$ as a machine for generating operator insertions. |
| 5 | Correlation functions | Scalar and spinning correlators, two- and three-point structures, four-point cross-ratios, and Lorentzian orderings. | You can write the general scalar two- and three-point functions and identify where dynamics first appears. |
| 6 | Radial quantization and representations | State-operator map, cylinder Hamiltonian, reflection positivity, conformal multiplets, and unitarity bounds. | You can explain why scaling dimensions are energies on $S^{d-1}\times\mathbb R$. |
| 7 | OPE, blocks, and bootstrap | OPE convergence, conformal blocks, crossing, positivity, lightcone bootstrap, and large spin. | You can turn an OPE into a four-point conformal block decomposition and state the crossing equation. |
| 8 | Essential 2D CFT | Complex coordinates, holomorphic factorization, $T(z)$, Virasoro, central charge, and free fields. | You can explain why $d=2$ has infinitely many local conformal transformations. |
| 9 | 2D CFT for strings and AdS$_3$ | Minimal models, modular invariance, Cardy formula, WZW models, Liouville, and noncompact CFT. | You can distinguish rational, compact, and noncompact 2D CFTs and explain why modular invariance matters. |
| 10 | Curved space, thermal CFT, and entanglement | CFT on the cylinder, Weyl anomaly, thermal CFT, KMS condition, modular Hamiltonians, replica trick, and entanglement. | You can explain why thermal CFT prepares black branes and why ball-shaped entanglement prepares Ryu--Takayanagi. |
| 11 | Symmetry, supersymmetry, and SCFT | Global symmetries, flavor currents, superconformal algebras, $R$-symmetry, BPS multiplets, and protected data. | You can identify protected operators and explain why supersymmetry makes some CFT data robust. |
| 12 | Large-$N$ CFT | Generalized free fields, single-trace and multi-trace operators, factorization, planar expansion, and large-$N$ perturbation theory. | You can explain why double-trace operators are two-particle bulk states. |
| 13 | $\mathcal N=4$ SYM and the AdS/CFT bridge | $\mathcal N=4$ SYM, $PSU(2,2|4)$, chiral primaries, Wilson loops, spin chains, and the pre-dictionary. | You can write the basic entries of the AdS$_5\times S^5$/CFT$_4$ dictionary. |
| 14 | Appendices | Notation, Lie algebra background, embedding-space formulas, supersymmetry cheatsheets, problem sets, glossary, and bibliography. | You know where to look when a convention or representation-theory fact blocks the main story. |

There is a deliberate asymmetry here. The two-dimensional part is serious, but it is not the spine of the course. The spine is higher-dimensional CFT language, because that is what one needs for AdS$_{d+1}$/CFT$_d$, especially AdS$_5$/CFT$_4$.

## The recommended reading strategy

There are three passes through this course.

### First pass: the skeleton

On a first pass, do not try to master every technical branch. Your job is to internalize the main chain:

$$
\text{RG fixed point}
\to
\text{conformal symmetry}
\to
\text{local operators}
\to
\text{correlators}
\to
\text{OPE}
\to
\text{large }N
\to
\text{holographic dictionary}.
$$

On this pass, focus on Modules 01--07, then Modules 12--13. Read Modules 08--11 more lightly, returning to them when they become relevant.

A healthy first-pass endpoint is the ability to explain the dictionary

$$
\boxed{
\mathcal O(x)\longleftrightarrow \phi(z,x),
\qquad
J(x)\longleftrightarrow \phi_{\partial}(x),
\qquad
\Delta(\Delta-d)=m^2L^2.
}
$$

You do not need to know every Witten diagram yet. You do need to know what $\mathcal O$, $J$, $\Delta$, $d$, $m$, and $L$ mean.

### Second pass: the working toolkit

On a second pass, do the exercises. Derive the two- and three-point functions. Work through the Ward identities. Check the unitarity bounds. Decompose at least one four-point function into conformal blocks. Learn why generalized free fields have disconnected correlators and double-trace towers.

The second pass should change the way you read AdS/CFT papers. When a paper says “single-trace scalar primary of dimension $\Delta$,” you should immediately see all of the following:

$$
\mathcal O
\quad\leftrightarrow\quad
\phi_{\rm bulk},
\qquad
\Delta
\quad\leftrightarrow\quad
m^2L^2,
\qquad
\langle \mathcal O\mathcal O\mathcal O\rangle
\quad\leftrightarrow\quad
\text{bulk cubic coupling}.
$$

When a paper says “large gap,” you should hear “bulk locality.” When it says “stress-tensor block,” you should hear “graviton exchange.” When it says “thermal state,” you should ask whether the bulk saddle is thermal AdS, an AdS black hole, or a black brane.

### Third pass: research fluency

On a third pass, follow one specialized path:

| Path | Modules | AdS/CFT direction |
|---|---|---|
| Bootstrap to bulk locality | 05--07, 12 | Large spin, crossing, anomalous dimensions, Witten diagrams, locality constraints. |
| $\mathcal N=4$ SYM | 11--13 | Protected data, superconformal multiplets, AdS$_5\times S^5$, integrability. |
| Black holes and real time | 03, 05, 10, 12 | Lorentzian correlators, thermal CFT, chaos, quasinormal modes, horizons. |
| Entanglement and geometry | 06, 10, 12 | Modular Hamiltonians, first law of entanglement, RT/HRT, bulk reconstruction. |
| Strings and AdS$_3$ | 08--09 | Virasoro symmetry, modular invariance, Cardy formula, WZW/Liouville, Brown-Henneaux. |

At this stage, the course is no longer just preparation. It becomes a reference system.

## The reference hierarchy

No single book is perfect for this course. The reason is structural: modern CFT for AdS/CFT combines material from critical phenomena, higher-dimensional conformal representation theory, 2D CFT, numerical and analytic bootstrap, supersymmetry, large-$N$ gauge theory, and holography.

Use references in layers.

### Layer 1: the core companions

These are the references to keep open while reading the main course.

| Reference | Best use | How to use it |
|---|---|---|
| S. Rychkov, *EPFL Lectures on Conformal Field Theory in $D\ge 3$ Dimensions* | Higher-dimensional CFT, operators, OPE, conformal blocks, bootstrap. | Use alongside Modules 03--07. It is one of the cleanest modern introductions to CFT in $d>2$. |
| D. Simmons-Duffin, *The Conformal Bootstrap* | Bootstrap logic, conformal blocks, radial quantization, numerical constraints. | Use after you know the basic kinematics. It is especially useful for Modules 06--07. |
| P. Di Francesco, P. Mathieu, D. Sénéchal, *Conformal Field Theory* | Deep 2D CFT: Virasoro, minimal models, modular invariance, WZW, cosets. | Use heavily for Modules 08--09, but do not let it replace the higher-dimensional spine. |
| O. Aharony, S. Gubser, J. Maldacena, H. Ooguri, Y. Oz, *Large $N$ Field Theories, String Theory and Gravity* | The classic AdS/CFT review. | Use after Modules 12--13. It rewards readers who already know CFT data and large-$N$ counting. |
| J. Penedones, *TASI Lectures on AdS/CFT* | Witten diagrams and the CFT meaning of bulk perturbation theory. | Use when transitioning from Module 12 to actual AdS computations. |

The most efficient pairing is:

$$
\boxed{
\text{this course for structure}
\quad+
\text{Rychkov/Simmons-Duffin for modern CFT}
\quad+
\text{DMS for }d=2
\quad+
\text{Aharony et al. for holography}.
}
$$

### Layer 2: specialized CFT references

Use these when a module becomes technical.

| Topic | References | Comments |
|---|---|---|
| General conformal correlators | H. Osborn and A. Petkou; F. Dolan and H. Osborn; M. Costa, J. Penedones, D. Poland, S. Rychkov | These are the workhorses for spinning correlators, conformal partial waves, and embedding-space methods. |
| Numerical bootstrap | S. Rychkov; D. Simmons-Duffin; D. Poland, S. Rychkov, A. Vichi review literature | The key ideas are crossing, unitarity, positivity, and semidefinite programming. |
| Analytic bootstrap | A. L. Fitzpatrick, J. Kaplan, D. Poland, D. Simmons-Duffin; Komargodski-Zhiboedov; Alday and collaborators | Read after conformal blocks and large spin feel natural. |
| 2D CFT basics | P. Ginsparg, *Applied Conformal Field Theory*; DMS | Ginsparg is short and sharp; DMS is comprehensive. |
| Modular invariance and Cardy formula | DMS; J. Cardy's original papers and lecture notes | Essential for AdS$_3$, black-hole entropy, and rational CFT. |
| WZW and affine algebras | DMS; Kac; Goddard-Kent-Olive coset literature | Necessary for strings on group manifolds and many exact 2D models. |
| Liouville/noncompact CFT | Teschner reviews; Zamolodchikov-Zamolodchikov literature | This is advanced; useful for noncompact worldsheets and AdS$_3$-adjacent topics. |

### Layer 3: AdS/CFT references

These become primary after the CFT course has built the needed dictionary.

| Topic | References | When to read |
|---|---|---|
| Original dictionary | Maldacena; Gubser-Klebanov-Polyakov; Witten | After Modules 04--05 and again after Module 13. The second reading is much better than the first. |
| Holographic renormalization | K. Skenderis lecture notes; de Haro-Skenderis-Solodukhin | After sources, Ward identities, and stress tensor are comfortable. |
| Large-$N$ gauge theory | 't Hooft; Coleman large-$N$ lectures; Aharony et al. | During Modules 12--13. |
| Thermal AdS/CFT | Witten on thermal phase transitions; Son-Starinets real-time prescription; Herzog review material | During Module 10 and after. |
| Entanglement and geometry | Ryu-Takayanagi; Hubeny-Rangamani-Takayanagi; Faulkner-Lewkowycz-Maldacena; Lashkari et al. | After modular Hamiltonians and stress-tensor Ward identities. |
| $\mathcal N=4$ SYM | Minwalla on superconformal representations; Beisert et al. integrability review; Ammon-Erdmenger textbook | During Module 13 and beyond. |

Do not read the original AdS/CFT papers as your first exposure to AdS/CFT unless you are already comfortable with CFT language. They are beautiful papers, but they are not beginner lecture notes. Their power is much clearer once you know what a source, a primary operator, a scaling dimension, and a connected correlator are.

## How to use Di Francesco--Mathieu--Sénéchal

The Di Francesco--Mathieu--Sénéchal book is a masterpiece, but it is not a blueprint for this course.

Its natural flow is:

$$
\text{2D critical systems}
\to
\text{local conformal maps}
\to
\text{Virasoro algebra}
\to
\text{minimal models}
\to
\text{modular invariance}
\to
\text{WZW models and cosets}.
$$

That is exactly the right flow for a course whose main aim is exact two-dimensional CFT. It is not the shortest route to AdS$_5$/CFT$_4$, large-$N$ CFT, or holographic correlators.

For this course, use DMS as follows:

| Course material | DMS role |
|---|---|
| Global conformal invariance | Useful comparison, but the course uses higher-dimensional conventions more directly adapted to AdS/CFT. |
| Ward identities and stress tensor | Very useful, especially in 2D language. |
| $T(z)$, Virasoro, central charge | Essential. DMS is the main deep reference. |
| Minimal models | Important as exact examples, but not the main AdS/CFT preparation path. |
| Modular invariance and Cardy formula | Essential for AdS$_3$/CFT$_2$ and black-hole entropy intuition. |
| WZW models and cosets | Important for string worldsheets and exact CFTs, but optional on a first pass if the goal is AdS$_5$/CFT$_4$. |
| Large-$N$ CFT and $\mathcal N=4$ SYM | Not the right source. Use modern AdS/CFT and SCFT references instead. |

A good rule is:

$$
\boxed{
\text{When this course says ``2D,'' open DMS. When it says ``large }N\text{,'' open holography references.}
}
$$

## How to read references without drowning

Reference overload is real. CFT has too many excellent sources, and not all of them are trying to teach the same subject. Use the following triage.

If a reference is giving definitions, read slowly. Definitions in CFT are compressed. A sentence like “let $\mathcal O$ be a scalar primary of dimension $\Delta$” carries representation theory, Ward identities, radial quantization, and OPE implications.

If a reference is deriving a universal kinematic formula, reproduce it. Examples include the two-point function, three-point function, stress-tensor Ward identity, unitarity bounds, and the scalar conformal block equation. These derivations become reusable muscle memory.

If a reference is classifying a large family of exact 2D theories, skim on a first pass unless your research needs it. Minimal-model tables, modular-invariant classifications, and affine-algebra branching rules are beautiful but can derail the AdS/CFT preparation route.

If a reference is computing model-specific coefficients, ask what principle it illustrates. For this course, the principle is often more important than the exact number.

A brutal but useful question is:

$$
\boxed{
\text{Does this page help me understand CFT data, Ward identities, OPE, large }N,
\text{ or the holographic dictionary?}
}
$$

If yes, read carefully. If no, mark it for later.

## The notation policy

Different CFT references use different conventions. This course tries to keep a stable notation adapted to AdS/CFT.

We use $d$ for the CFT spacetime dimension and $d+1$ for the AdS dimension. Thus AdS$_{d+1}$/CFT$_d$ means:

$$
\text{bulk dimension}=d+1,
\qquad
\text{boundary CFT dimension}=d.
$$

We use $L$ for the AdS radius when it is needed, and often set $L=1$ in intermediate formulas. Scaling dimensions are denoted by $\Delta$. Spin is usually $\ell$. The stress tensor is $T_{\mu\nu}$, conserved currents are $J_\mu$, and generic scalar primaries are $\mathcal O$.

In Euclidean CFT, the conformal group is often written as $SO(d+1,1)$. In Lorentzian CFT, it is $SO(d,2)$, which is also the isometry group of AdS$_{d+1}$. Because this course is aimed at AdS/CFT, $SO(d,2)$ will often be the default notation when discussing the physical conformal group.

For two-dimensional CFT, we use complex coordinates

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2,
$$

and conformal weights $(h,\bar h)$, related to scaling dimension and spin by

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

For $\mathcal N=4$ SYM, the gauge group will usually be $SU(N)$, the 't Hooft coupling is

$$
\lambda=g_{\rm YM}^2N,
$$

and the planar limit is

$$
N\to\infty,
\qquad
\lambda\;\text{fixed}.
$$

The appendices collect these conventions so that the main lecture pages do not have to pause every time a notation clash appears.

## What to skip on a first pass

Skipping is not laziness. It is good navigation.

On a first pass, you may safely postpone detailed proofs of the Kac determinant, ADE classifications of modular invariants, full affine Lie algebra representation theory, explicit semidefinite programming implementation, detailed superconformal index technology, and spin-chain integrability beyond the basic $SU(2)$ sector.

But do not skip the following:

$$
\boxed{
\text{stress tensor},
\quad
\text{sources},
\quad
\text{Ward identities},
\quad
\text{state-operator map},
\quad
\text{OPE},
\quad
\text{crossing},
\quad
\text{large }N.
}
$$

Those are the load-bearing beams. If they are shaky, AdS/CFT becomes a memorized dictionary rather than a working framework.

## How the website pages should be read

Every lecture page is designed to have a similar rhythm.

First comes motivation: why the topic matters, especially for AdS/CFT. Then come definitions and derivations. Then comes an AdS/CFT checkpoint, which states explicitly how the topic will later reappear in holography. Finally, there are exercises with solutions.

The exercises are not ornamental. A reader who only reads CFT passively will recognize formulas but fail to use them. This is particularly dangerous in AdS/CFT, where many computations are dictionary translations. The exercises train the translations.

For example, the source coupling

$$
S_{\rm CFT}\to S_{\rm CFT}+\int d^d x\,J(x)\mathcal O(x)
$$

is not just a QFT convention. It is the seed of

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}[\phi_{\partial}=J].
$$

A student who has differentiated $Z[J]$ several times by hand will understand this equation much more deeply than a student who only memorizes it.

## A minimal twelve-week route

For a one-semester reading course, the following compressed route works well.

| Week | Focus | Pages/modules |
|---:|---|---|
| 1 | Orientation, QFT data, signatures | Module 01 |
| 2 | RG fixed points and stress-tensor trace | Module 02 |
| 3 | Conformal group and conformal geometry | Module 03 |
| 4 | Operators, sources, Ward identities | Module 04 |
| 5 | Two- and three-point functions, spinning basics | Module 05 |
| 6 | Four-point functions, Lorentzian correlators | Module 05 |
| 7 | Radial quantization and unitarity bounds | Module 06 |
| 8 | OPE, conformal blocks, crossing | Module 07 |
| 9 | Essential 2D CFT: $T(z)$ and Virasoro | Module 08 |
| 10 | Thermal CFT and entanglement | Module 10 |
| 11 | Large-$N$ CFT and generalized free fields | Module 12 |
| 12 | $\mathcal N=4$ SYM and the pre-dictionary | Module 13 |

This route is aggressive. It is best for students whose goal is to start AdS/CFT as soon as possible. A slower route should spend two extra weeks on Modules 06--07 and two extra weeks on Module 12.

## A research-oriented route

For a student preparing to work on holographic correlators, the priority should be:

$$
05\to06\to07\to12\to13.
$$

For a student preparing to work on black holes, chaos, or real-time holography:

$$
03\to05\to10\to12.
$$

For a student preparing to work on AdS$_3$/CFT$_2$:

$$
08\to09\to10.
$$

For a student preparing to work on supersymmetric holography:

$$
11\to13,
$$

with Modules 04--07 as non-negotiable background.

For a student preparing to work on quantum information in holography:

$$
06\to10\to12,
$$

plus the stress-tensor and modular-Hamiltonian material from Modules 04 and 05.

## Diagnostic questions before starting AdS/CFT

Before moving to an AdS/CFT course, try answering these questions without notes.

What is a primary operator? What is the difference between a scaling dimension and an engineering dimension? What is the meaning of the OPE coefficient $C_{ijk}$? Why are two-point functions diagonal in scaling dimension in a unitary CFT? What does radial quantization do to the dilatation operator? How does a conserved current saturate a unitarity bound? What information is contained in a four-point function beyond conformal symmetry? Why is crossing symmetry an associativity condition? What is a generalized free field? Why do double-trace operators appear at large $N$? Why does $T_{\mu\nu}$ correspond to the graviton? Why is the source $J$ identified with the boundary value of a bulk field?

If these questions feel answerable, the AdS/CFT dictionary will feel natural. If they feel mysterious, the next AdS/CFT paper will look like a magic trick.

## Exercises

### Exercise 1

A CFT contains a scalar primary $\mathcal O$ of dimension $\Delta$. List the minimum CFT data involving $\mathcal O$ that one would want to know before trying to interpret it as a weakly coupled bulk scalar field.

<details><summary><strong>Solution</strong></summary>

At minimum, one wants the two-point normalization, the dimension $\Delta$, global-symmetry representation labels, and the OPE coefficients involving $\mathcal O$.

The dimension gives the bulk mass through

$$
\Delta(\Delta-d)=m^2L^2
$$

for a scalar in standard quantization. The two-point normalization fixes the normalization of the dual bulk field. The three-point coefficients $C_{\mathcal O\mathcal O\mathcal O_k}$ determine cubic bulk couplings or exchange data. The four-point function of $\mathcal O$ probes interactions, double-trace anomalous dimensions, and whether the putative bulk theory is local at low energies.

In a holographic large-$N$ CFT, one also asks whether $\mathcal O$ is single-trace, how its connected correlators scale with $N$, and whether there is a large gap above the light single-trace spectrum.

</details>

### Exercise 2

Why is it not enough to learn only two-dimensional CFT before learning AdS$_5$/CFT$_4$?

<details><summary><strong>Solution</strong></summary>

Two-dimensional CFT teaches crucial ideas: local conformal symmetry, Virasoro symmetry, central charge, modular invariance, exact solvability, and worldsheet methods. These are essential for strings and AdS$_3$/CFT$_2$.

But AdS$_5$/CFT$_4$ requires higher-dimensional CFT technology. The boundary theory is four-dimensional $\mathcal N=4$ SYM. Its conformal group is $SO(4,2)$ in Lorentzian signature. Its local operators organize into representations of the four-dimensional superconformal algebra, not merely Virasoro modules. Large-$N$ factorization, single-trace operators, multi-trace towers, and the large-$N$ OPE are central. These are not the main focus of a classic 2D CFT course.

So 2D CFT is necessary for some holographic directions, but insufficient as the only preparation for AdS/CFT.

</details>

### Exercise 3

A student says: “The AdS/CFT dictionary is just $\mathcal O\leftrightarrow\phi$.” Explain why this is too crude.

<details><summary><strong>Solution</strong></summary>

The correspondence $\mathcal O\leftrightarrow\phi$ is only the first entry. The sharper statement involves sources and generating functionals:

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}[\phi_{\partial}=J].
$$

This means that CFT correlators are obtained by differentiating with respect to sources:

$$
\langle \mathcal O(x_1)\cdots\mathcal O(x_n)\rangle
=
\frac{\delta^n \log Z_{\rm CFT}[J]}{\delta J(x_1)\cdots \delta J(x_n)}\bigg|_{J=0}.
$$

On the bulk side, the same derivatives compute the response of the on-shell bulk action to boundary values. The relation also includes

$$
\Delta(\Delta-d)=m^2L^2,
$$

normalization choices, boundary conditions, regularity or infalling conditions, counterterms, and operator mixing. The slogan $\mathcal O\leftrightarrow\phi$ is useful, but the real dictionary is a statement about generating functionals and CFT data.

</details>

### Exercise 4

Design a personal reading route for one of the following goals: holographic correlators, AdS$_3$/CFT$_2$, black-hole physics, supersymmetric holography, or entanglement and bulk reconstruction.

<details><summary><strong>Solution</strong></summary>

One possible answer for holographic correlators is:

$$
03\to04\to05\to06\to07\to12\to13.
$$

The logic is: conformal geometry fixes the kinematics; Ward identities and sources define what the CFT computes; correlators and OPE define the observable data; radial quantization and unitarity organize the spectrum; conformal blocks and crossing describe exchange; large-$N$ CFT explains why bulk perturbation theory emerges; $\mathcal N=4$ SYM supplies the canonical example.

One possible answer for AdS$_3$/CFT$_2$ is:

$$
08\to09\to10,
$$

with Modules 04--07 used as background. The logic is: Virasoro symmetry and central charge are central in $d=2$; modular invariance and the Cardy formula control high-energy states; thermal CFT and entanglement connect to BTZ black holes and holographic entropy.

</details>

## Summary

The course is designed around the path

$$
\boxed{
\text{local QFT}
\to
\text{RG fixed point}
\to
\text{conformal symmetry}
\to
\text{operator data}
\to
\text{OPE and crossing}
\to
\text{large }N
\to
\text{AdS/CFT}.
}
$$

The references are tools, not the structure. Use modern higher-dimensional CFT notes for the main spine, DMS for the deep two-dimensional machinery, and holography references once the CFT dictionary is no longer just a slogan.

The next module begins the actual physics: Wilsonian RG, fixed points, and why a CFT is the universal local description of a scale-invariant critical point.
