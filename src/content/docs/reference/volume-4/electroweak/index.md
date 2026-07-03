---
title: "Electroweak Theory"
description: "Chapter overview for the SU(2)L × U(1)Y gauge theory of weak isospin and hypercharge, its chiral matter couplings, electroweak symmetry breaking, W and Z bosons, charged and neutral currents, and the Fermi limit."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 28–31; Weinberg Vol. II electroweak chapters; Coleman, Aspects of Symmetry, Ch. 5."
topics:
  - electroweak theory
  - weak isospin
  - hypercharge
  - electroweak symmetry breaking
  - W and Z bosons
  - weak currents
  - Fermi theory
canonicalTopics:
  - electroweak-theory
  - su2-u1-gauge-structure
  - weak-isospin
  - hypercharge
  - electroweak-symmetry-breaking
  - charged-current
  - neutral-current
researchStatus:
  established:
    - "The electroweak interaction is described by a chiral SU(2)L × U(1)Y gauge theory whose Higgs vacuum leaves an unbroken electromagnetic U(1)."
  active:
    - "Precision electroweak fits, neutrino-sector extensions, flavor anomalies, Higgs-coupling measurements, and SMEFT interpretations remain active interfaces between electroweak theory and experiment."
---

Electroweak Theory is the chapter where gauge theory becomes the unified description of weak and electromagnetic interactions. Before symmetry breaking, the theory is not QED plus a separate weak force. It is a chiral gauge theory with gauge group

$$
SU(2)_L\times U(1)_Y.
$$

The weak gauge bosons $W_\mu^a$ couple to weak-isospin generators $T^a$, while the hypercharge gauge boson $B_\mu$ couples to $Y$. The Higgs vacuum then selects the unbroken generator

$$
Q=T^3+Y,
$$

so that the photon, $W^\pm$, and $Z$ boson are not put in by hand. They are the mass eigenstate fields produced by the breaking pattern

$$
SU(2)_L\times U(1)_Y
\longrightarrow
U(1)_{\rm em}.
$$

This chapter explains that architecture in stages: the gauge group, weak isospin and hypercharge, the covariant derivative, the Higgs vacuum, the physical gauge bosons, charged and neutral currents, and the low-energy Fermi theory.

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the default convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
F_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

You should also know the Gauge Principle chapter through [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/) and [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/), plus the Yang–Mills chapter through [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/).

For the quantum field theory side, the Gauge Quantization and Gauge Renormalization chapters explain why chiral gauge theories require gauge fixing, ghosts, BRST identities, and anomaly cancellation. For the strong-interaction contrast, the [Quantum Chromodynamics](/gauge-theories-standard-model/qcd/) chapter is helpful: QCD is vectorlike and unbroken, while the electroweak theory is chiral and Higgsed.

## Reading path

Read these pages in order on a first pass. All eight pages are available now; the Fermi-theory page closes the first-pass chapter arc.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [SU(2)L × U(1)Y Gauge Structure](/gauge-theories-standard-model/electroweak/su2-u1-gauge-structure/) | The gauge group, gauge fields, generators, couplings, representation data, and the reason hypercharge is not ordinary electric charge. |
| 2 | [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/) | How $T^3$ and $Y$ combine to produce observed charges, and why left-handed doublets and right-handed singlets have different electroweak quantum numbers. |
| 3 | [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/) | The full covariant derivative on quarks, leptons, and the Higgs doublet, including color when needed. |
| 4 | [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) | How the Higgs vacuum selects $U(1)_{\rm em}$ and converts gauge-eigenstate fields into massive and massless combinations. |
| 5 | [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) | The definitions of $A_\mu$, $Z_\mu$, and $W_\mu^\pm$, their masses, polarizations, and couplings. |
| 6 | [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/) | The $W^\pm$ interactions, chiral structure, lepton currents, CKM mixing, and the origin of charged weak transitions. |
| 7 | [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/) | The $Z$ couplings, vector and axial currents, weak mixing angle dependence, and the absence of tree-level flavor-changing neutral currents. |
| 8 | [Fermi Theory Limit](/gauge-theories-standard-model/electroweak/fermi-theory-limit/) | How integrating out the $W$ and $Z$ at low momentum gives four-fermion weak interactions and the relation between $G_F$, $v$, $m_W$, and $m_Z$. |

The chapter deliberately starts before symmetry breaking. Otherwise the photon and $Z$ boson look like arbitrary mixtures, and the weak mixing angle looks like a trick rather than a consequence of two gauge couplings and one unbroken generator.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| $SU(2)_L$ | The weak-isospin gauge factor. | Acts nontrivially on left-handed fermion doublets and the Higgs doublet. |
| $U(1)_Y$ | The hypercharge gauge factor. | Supplies the second neutral gauge boson and combines with $T^3$ to give electric charge after symmetry breaking. |
| $W_\mu^a$ | The three $SU(2)_L$ gauge fields, $a=1,2,3$. | Become $W^\pm$ and part of the $Z$–photon mixture. |
| $B_\mu$ | The $U(1)_Y$ gauge field. | Mixes with $W_\mu^3$ after electroweak symmetry breaking. |
| $g$ and $g'$ | The $SU(2)_L$ and $U(1)_Y$ gauge couplings. | Determine the weak mixing angle and the electric charge $e$. |
| $T^a$ | Weak-isospin generators. | In doublets, $T^a=\sigma^a/2$; in singlets, $T^a=0$. |
| $Y$ | Hypercharge. | A representation label fixed by electric charges, Yukawa couplings, and anomaly cancellation. |
| $Q=T^3+Y$ | Electric charge generator in this convention. | The unbroken generator after the Higgs doublet takes a neutral vacuum expectation value. |
| $H$ | The Higgs doublet with $Y=1/2$. | Its lower neutral component preserves $Q$ and gives masses to $W^\pm$ and $Z$. |
| $\theta_W$ | The weak mixing angle. | Relates $W^3_\mu$, $B_\mu$ to $A_\mu$, $Z_\mu$, and satisfies $e=g\sin\theta_W=g'\cos\theta_W$. |
| Charged current | The interaction mediated by $W^\pm$. | Changes weak isospin and is purely left-chiral in the minimal Standard Model. |
| Neutral current | The interaction mediated by $Z$. | Does not change electric charge but distinguishes weak isospin and hypercharge. |

The landmarks divide into three layers: the unbroken gauge input, the Higgs-selected electromagnetic output, and the current interactions that experiments see.

## Common confusions

**Electroweak theory is not QED plus massive weak bosons.** QED appears after the Higgs vacuum selects an unbroken $U(1)_{\rm em}$. Before symmetry breaking, the neutral gauge fields are $W_\mu^3$ and $B_\mu$, not the photon and $Z$ boson.

**The subscript L in $SU(2)_L$ is physical.** Weak isospin acts on left-handed fermion doublets. Right-handed charged fermions are weak-isospin singlets in the minimal Standard Model. This chiral structure is why anomaly cancellation is a nontrivial consistency condition.

**Hypercharge is not electric charge.** Hypercharge is the charge of $U(1)_Y$. Electric charge is the combination $Q=T^3+Y$ that remains unbroken after the Higgs field chooses a vacuum direction.

**The photon is massless because of an unbroken gauge symmetry, not because $B_\mu$ was already the photon.** The massless field is the unbroken linear combination of $W_\mu^3$ and $B_\mu$.

**Gauge symmetry is not spontaneously broken in the same sense as a global symmetry.** The gauge redundancy remains. What changes is the organization of gauge-invariant excitations and the convenient field variables used to describe massive vector bosons.

**The weak mixing angle is not a representation label.** It is determined by the two gauge couplings, not by the weak-isospin or hypercharge assignments of a particular field.

**QCD color and weak isospin are independent gauge structures.** Quark doublets carry both color and electroweak charges, but color does not participate in electroweak symmetry breaking.

## Boundaries

This chapter does:

- formulate the electroweak gauge theory using $SU(2)_L\times U(1)_Y$;
- explain weak isospin, hypercharge, and the convention $Q=T^3+Y$;
- derive the basic gauge-boson mixing structure after the Higgs vacuum;
- explain charged and neutral weak currents;
- connect the low-energy weak interaction to the Fermi theory;
- prepare the Higgs Sector, Flavor and Neutrinos, Standard Model Architecture, and Anomalies chapters.

This chapter does not try to:

- give precision electroweak numerical fits or current global-fit tables;
- derive the full Higgs-sector phenomenology, which has its own chapter;
- cover CKM and PMNS mixing in full detail, which belongs in the Flavor and Neutrinos chapter;
- prove anomaly cancellation, which belongs in the Standard Model anomalies chapter;
- replace collider phenomenology or PDG-style data tables;
- treat beyond-Standard-Model electroweak extensions except as brief signposts.

The chapter’s job is to make the Standard Model’s weak and electromagnetic gauge structure feel inevitable rather than memorized.

## Where to go next

After this chapter, continue to the [Higgs Sector](/gauge-theories-standard-model/higgs-sector/) chapter for a more focused treatment of the Higgs mechanism, gauge-boson masses, Higgs couplings, and the Goldstone equivalence theorem.

Then continue to Flavor and Neutrinos for Yukawa matrices, CKM mixing, CP violation, PMNS mixing, and the Weinberg operator. The Standard Model Architecture chapter later assembles color, electroweak theory, Higgs physics, flavor, and anomaly cancellation into the full Lagrangian.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§87–91, for the Standard Model gauge and Higgs sector, lepton sector, quark sector, electroweak interactions of hadrons, and neutrino masses.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–31, for spontaneous symmetry breaking, weak interactions, anomalies, and precision electroweak tests.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for spontaneously broken gauge symmetries and the electroweak theory.

### Deeper references

- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a conceptual route from gauge fields and the Higgs phenomenon to massive vector bosons.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for the standard electroweak Lagrangian, gauge-boson masses, and tree-level weak processes.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a compact and physically sharp account of weak currents and electroweak unification.
- Burgess, *Introduction to Effective Field Theory*, for the low-energy Fermi theory and the Standard Model viewed as an effective theory.

## Version history

- **2026-06-18:** Linked the Fermi Theory Limit page and the new Higgs Sector chapter overview.
- **2026-06-18:** Linked the weak-charged-current and weak-neutral-current pages in the reading path.
- **2026-06-18:** Linked the electroweak-symmetry-breaking and photon-W-Z-bosons pages in the reading path.
- **2026-06-18:** Linked the weak-isospin/hypercharge and electroweak-covariant-derivative pages in the reading path.
- **2026-06-18:** Initial chapter overview. Added the first-pass electroweak reading path and linked the gauge-structure page.
