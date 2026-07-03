---
title: "Fermi Theory Limit"
description: "Derives the low-energy four-fermion weak interaction by integrating out W and Z bosons, fixing the normalization of G_F and explaining the effective-field-theory expansion."
sidebar:
  label: "Fermi Theory Limit"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–90; Schwartz Chs. 22 and 29; Weinberg Vol. II electroweak chapters; Burgess Chs. 7 and 9."
topics:
  - Fermi theory
  - weak interactions
  - integrating out heavy fields
  - four-fermion operators
  - low-energy effective field theory
canonicalTopics:
  - fermi-theory
  - weak-interaction-effective-theory
  - integrating-out-w-boson
  - four-fermion-operator
  - fermi-constant
researchStatus:
  established:
    - "At momenta much smaller than m_W and m_Z, tree-level electroweak exchange reduces to local four-fermion interactions with G_F/√2 = g²/(8m_W²) = 1/(2v²)."
  active:
    - "Precision weak decays require radiative corrections, hadronic matrix elements, neutrino masses, and SMEFT corrections beyond the tree-level Fermi limit."
---

## Summary

The Fermi theory limit is the low-energy shadow of the electroweak theory. When all momentum transfers are small compared with $m_W$ and $m_Z$, the massive weak bosons cannot be resolved as propagating particles. Their exchange collapses into local four-fermion operators.

For charged currents, the result is

$$
\mathcal L_{\rm F}^{\rm cc}
=
-\frac{g^2}{2m_W^2}J_+^\mu J_{-\mu}
=
-\frac{4G_F}{\sqrt2}J_+^\mu J_{-\mu},
$$

with

$$
\frac{G_F}{\sqrt2}=\frac{g^2}{8m_W^2}=\frac{1}{2v^2}
$$

at tree level in the minimal Standard Model. For example, muon decay is described by

$$
\mathcal L_{\rm F}^{\mu\text{-decay}}
=
-\frac{4G_F}{\sqrt2}
(\bar\nu_{\mu L}\gamma^\mu\mu_L)
(\bar e_L\gamma_\mu\nu_{eL}).
$$

Equivalently, using $P_L=(1-\gamma^5)/2$ inside Dirac bilinears,

$$
\mathcal L_{\rm F}^{\mu\text{-decay}}
=
-\frac{G_F}{\sqrt2}
(\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu)
(\bar e\gamma_\mu(1-\gamma^5)\nu_e).
$$

The two forms are the same. The factor of $4$ is just the price of writing left-handed fields either as explicit Weyl components or as Dirac fields with $(1-\gamma^5)$ rather than $P_L$.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Fermi theory matching](/figures/gauge-theories-standard-model/fermi-theory-matching.svg)

<figcaption>

The Fermi limit is tree-level matching. At $q^2\ll m_W^2$, the nonlocal $W$ propagator becomes a local contact interaction. The leading coefficient is $g^2/(2m_W^2)$ for left-chiral currents, or $4G_F/\sqrt2$ with $G_F/\sqrt2=g^2/(8m_W^2)$.

</figcaption>
</figure>

This page is not a precision-decay calculation. Its job is to show exactly how the low-energy weak interaction emerges from the Standard Model, what normalization is being used, and where the effective theory stops being reliable.

## Prerequisites

You should know the electroweak pages on [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/) and [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/). The relations among $g$, $g'$, $e$, $m_W$, $m_Z$, and $v$ are derived in [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/).

For the effective-field-theory interpretation, it helps to know the basic distinction between a full theory and a low-energy effective theory: heavy fields can be removed from the low-energy spectrum, but their effects remain as local operators suppressed by powers of their masses.

## Core idea

A propagator is nonlocal. A contact operator is local. The Fermi limit is the statement that a very massive propagator looks local to low-energy probes.

The relevant expansion is schematically

$$
\frac{1}{q^2-m_W^2}
=
-\frac{1}{m_W^2}\left(1+\frac{q^2}{m_W^2}+\cdots\right),
\qquad |q^2|\ll m_W^2.
$$

The first term gives the dimension-six four-fermion Fermi interaction. The next terms give higher-derivative operators, suppressed by additional powers of $q^2/m_W^2$.

Thus the Fermi theory is not a rival to the electroweak theory. It is the first terms in the electroweak theory’s low-energy expansion:

$$
\text{electroweak theory}
\quad\xrightarrow{|q|\ll m_W,m_Z}\quad
\text{Fermi theory plus higher-dimensional operators}.
$$

Historically, Fermi theory came first. Conceptually, in the modern Standard Model, it is an effective field theory obtained by integrating out $W$ and $Z$ bosons.

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu,
$$

so a fermion kinetic term gives interactions with an overall minus sign:

$$
i\bar\psi\gamma^\mu D_\mu\psi
\supset
-gW_\mu^a\bar\psi\gamma^\mu T^a\psi
-g'B_\mu\bar\psi\gamma^\mu Y\psi.
$$

The charged-current interaction is written

$$
\mathcal L_{\rm cc}
=
-\frac{g}{\sqrt2}
\left(W_\mu^+J_+^\mu+W_\mu^-J_-^\mu\right),
\qquad
J_-^\mu=(J_+^\mu)^\dagger.
$$

For leptons,

$$
J_+^\mu\supset \bar\nu_{\ell L}\gamma^\mu\ell_L,
\qquad
J_-^\mu\supset \bar\ell_L\gamma^\mu\nu_{\ell L}.
$$

For quarks in the mass basis,

$$
J_+^\mu\supset \bar u_{iL}\gamma^\mu V_{ij}d_{jL},
\qquad
J_-^\mu\supset \bar d_{jL}\gamma^\mu V_{ij}^*u_{iL},
$$

where $V$ is the CKM matrix.

The weak-boson masses are

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{\sqrt{g^2+g'^2}\,v}{2}
=\frac{m_W}{c_W}.
$$

These relations are tree-level Standard Model relations. Loop corrections and input-scheme conventions are part of precision electroweak theory, not the tree-level matching argument on this page.

## Integrating out the W boson

At energies well below $m_W$, ignore derivatives in the $W$ kinetic operator for the leading matching. The relevant algebraic part of the Lagrangian is

$$
\mathcal L[W,J]
\simeq
m_W^2 W_\mu^+W^{-\mu}
-\frac{g}{\sqrt2}\left(W_\mu^+J_+^\mu+W_\mu^-J_-^\mu\right).
$$

Treat $W^+$ and $W^-$ as conjugate complex fields. Their algebraic equations of motion are

$$
m_W^2W_\mu^- = \frac{g}{\sqrt2}J_{+\mu},
\qquad
m_W^2W_\mu^+ = \frac{g}{\sqrt2}J_{-\mu}.
$$

Substituting back gives

$$
\mathcal L_{\rm eff}^{\rm cc}
=
-\frac{g^2}{2m_W^2}J_+^\mu J_{-\mu}
+O\!\left(\frac{\partial^2}{m_W^4}\right).
$$

Using $m_W=gv/2$,

$$
\frac{g^2}{2m_W^2}
=
\frac{2}{v^2}.
$$

The conventional Fermi constant is defined by

$$
\frac{g^2}{2m_W^2}=\frac{4G_F}{\sqrt2},
$$

so

$$
\boxed{
\frac{G_F}{\sqrt2}=\frac{g^2}{8m_W^2}=\frac{1}{2v^2}
}
$$

at tree level.

The boxed formula is the main normalization result. It is also the bridge between a low-energy weak-decay measurement and the electroweak scale $v$.

## Muon decay and the factor of four

The classic charged-current example is

$$
\mu^-\to e^-\bar\nu_e\nu_\mu.
$$

From the general charged-current operator,

$$
\mathcal L_{\rm eff}^{\rm cc}
=
-\frac{4G_F}{\sqrt2}J_+^\mu J_{-\mu},
$$

select

$$
J_+^\mu\supset \bar\nu_{\mu L}\gamma^\mu\mu_L,
\qquad
J_-^\mu\supset \bar e_L\gamma^\mu\nu_{eL}.
$$

Then

$$
\mathcal L_{\rm F}^{\mu\text{-decay}}
=
-\frac{4G_F}{\sqrt2}
(\bar\nu_{\mu L}\gamma^\mu\mu_L)
(\bar e_L\gamma_\mu\nu_{eL}).
$$

This is the cleanest expression if all fields are explicitly left-handed.

Many books instead write the same operator using Dirac fields and $(1-\gamma^5)$:

$$
\bar\nu_{\mu L}\gamma^\mu\mu_L
=
\bar\nu_\mu\gamma^\mu P_L\mu
=
\frac12\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu.
$$

The second bilinear contributes another factor of $1/2$, so

$$
4(\bar\nu_{\mu L}\gamma^\mu\mu_L)
(\bar e_L\gamma_\mu\nu_{eL})
=
(\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu)
(\bar e\gamma_\mu(1-\gamma^5)\nu_e).
$$

Therefore the same Lagrangian is

$$
\mathcal L_{\rm F}^{\mu\text{-decay}}
=
-\frac{G_F}{\sqrt2}
(\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu)
(\bar e\gamma_\mu(1-\gamma^5)\nu_e).
$$

This is why two equally standard-looking formulas differ by a factor of $4$. One uses left-handed bilinears. The other uses Dirac bilinears with $(1-\gamma^5)$.

## Beta decay and CKM factors

For semileptonic charged-current processes, the quark part of $J_+^\mu$ contains the CKM matrix:

$$
J_+^\mu\supset \bar u_{iL}\gamma^\mu V_{ij}d_{jL}.
$$

The low-energy charged-current operator contains terms such as

$$
\mathcal L_{\rm eff}^{\rm semileptonic}
=
-\frac{4G_F}{\sqrt2}
(\bar\nu_{\ell L}\gamma^\mu\ell_L)
(\bar d_{jL}\gamma_\mu V_{ij}^*u_{iL})
+\text{h.c.}
$$

For neutron beta decay, the relevant quark transition is $d\to u$, so the coefficient contains $V_{ud}$. At the quark level one may write the operator schematically as

$$
-\frac{4G_F}{\sqrt2}V_{ud}^*
(\bar e_L\gamma_\mu\nu_{eL})(\bar u_L\gamma^\mu d_L)
+\text{h.c.},
$$

up to the convention for which term is called the operator and which is called its Hermitian conjugate.

The quark-level operator is not yet a neutron decay rate. The hadronic part must be evaluated between neutron and proton states:

$$
\langle p|\bar u\gamma^\mu(1-\gamma^5)d|n\rangle.
$$

That matrix element contains form factors and strong-interaction physics. The Fermi limit supplies the short-distance weak operator; QCD supplies the hadronic matrix element. Confusing those two jobs is a classic way to make beta decay look simpler than it is.

## Neutral-current contact interactions

The $Z$ boson also produces low-energy four-fermion interactions. The neutral-current interaction is

$$
\mathcal L_Z
=
-\frac{g}{c_W}Z_\mu J_Z^\mu,
\qquad
J_Z^\mu
=
\sum_f\bar f\gamma^\mu(T_f^3P_L-s_W^2Q_f)f.
$$

At leading order in $q^2/m_Z^2$, integrating out the real massive vector field $Z_\mu$ gives

$$
\mathcal L_{\rm eff}^{\rm nc}
=
-\frac{g^2}{2c_W^2m_Z^2}J_Z^\mu J_{Z\mu}
+O\!\left(\frac{\partial^2}{m_Z^4}\right).
$$

Using

$$
m_Z=\frac{gv}{2c_W},
$$

this becomes

$$
\mathcal L_{\rm eff}^{\rm nc}
=
-\frac{2}{v^2}J_Z^\mu J_{Z\mu}
=
-\frac{4G_F}{\sqrt2}J_Z^\mu J_{Z\mu}.
$$

The factor of $1/2$ in the intermediate expression is not optional: it comes from integrating out a real field with a mass term $\frac12m_Z^2Z_\mu Z^\mu$. When one expands $J_Z^2$ into two different currents, cross terms bring their own factor of $2$.

Neutral-current contact interactions are important in low-energy neutrino scattering, atomic parity violation, and other precision weak processes. The full phenomenology requires radiative corrections and process-specific matrix elements, but the tree-level contact operator follows immediately from $Z$ exchange.

## The EFT expansion

The Fermi interaction has mass dimension six. A four-fermion operator has dimension

$$
[\bar\psi\psi\bar\chi\chi]=6,
$$

so its coefficient has dimension $-2$. This is why the coefficient is set by $1/m_W^2$ or $1/v^2$.

The leading charged-current Fermi theory is therefore only the first term in an expansion:

$$
\mathcal L_{\rm eff}
=
\mathcal L_{\rm QED+QCD}^{\rm light}
-\frac{4G_F}{\sqrt2}J_+\cdot J_-
-\frac{4G_F}{\sqrt2}J_Z\cdot J_Z
+\sum_i\frac{c_i}{m_W^4}\mathcal O_i^{(8)}+\cdots.
$$

The dimension-eight terms contain extra derivatives or additional powers of light masses. In a scattering amplitude they are suppressed by powers such as

$$
\frac{q^2}{m_W^2},
\qquad
\frac{m_f^2}{m_W^2}.
$$

At very low energies this is an excellent approximation. Near the weak scale it is not.

This is a useful place to separate two meanings of “renormalizable.” The Fermi theory is perfectly usable as an effective field theory: it can be renormalized order by order in powers of $E/m_W$. But it is not renormalizable in the old strict sense that finitely many parameters determine arbitrarily high-energy predictions. The Standard Model resolves that high-energy failure by replacing the contact interaction with propagating $W$ and $Z$ bosons inside a gauge theory.

## Why the Fermi theory had to fail at high energy

The Fermi interaction makes amplitudes grow with energy. Dimensional analysis already says that a four-fermion amplitude behaves like

$$
\mathcal M\sim G_FE^2
$$

when external masses are negligible. This growth cannot continue forever without violating perturbative unitarity.

In the electroweak theory, the contact vertex is replaced by the propagator

$$
\frac{1}{q^2-m_W^2}
$$

and by the gauge structure that controls high-energy longitudinal-vector behavior. The $W$ and $Z$ bosons are not decorative. They are the degrees of freedom needed to extend the low-energy weak interaction into a consistent relativistic quantum field theory at electroweak energies.

The Higgs sector is part of the same story. It gives masses to $W$ and $Z$ while preserving gauge-theory consistency, and it controls the high-energy behavior of longitudinal weak-boson scattering.

## Matching versus measuring

The tree-level matching relation

$$
\frac{G_F}{\sqrt2}=\frac{1}{2v^2}
$$

says that the low-energy Fermi constant determines the electroweak scale $v$ in the tree-level Standard Model.

Precision electroweak physics refines this statement. In real calculations, one must choose an input scheme and include radiative corrections. Then quantities such as $G_F$, $m_Z$, $\alpha$, $m_W$, and $\sin^2\theta_W$ are related by loop-corrected formulas. The tree-level formula remains the conceptual anchor, but precision work replaces it with a controlled perturbative relation.

For this chapter, the important lesson is simpler:

$$
\boxed{
\text{low-energy weak strength}
\quad\Longleftrightarrow\quad
\text{electroweak scale }v
}
$$

The Fermi constant is not just a decay parameter. It is the low-energy way of measuring the scale of electroweak symmetry breaking.

## Common pitfalls

**Mixing $P_L$ and $(1-\gamma^5)$ without changing coefficients.** If the operator is written with left-handed fields, the charged-current coefficient is $4G_F/\sqrt2$. If it is written with $(1-\gamma^5)$ in each bilinear, the conventional coefficient is $G_F/\sqrt2$.

**Forgetting the CKM matrix in semileptonic charged currents.** In the quark mass basis, charged currents contain $V_{ij}$. Neutral currents do not contain tree-level flavor-changing CKM factors.

**Treating Fermi theory as valid near the weak scale.** The expansion parameter is roughly $q^2/m_W^2$. Once the momentum transfer can resolve a $W$ or $Z$, the contact approximation is the wrong description.

**Thinking the Fermi theory explains weak-boson masses.** It does not. It parameterizes their low-energy effects. The origin of $m_W$ and $m_Z$ is the Higgs mechanism.

**Ignoring hadronic matrix elements.** A quark-level weak operator is not automatically a hadron-level prediction. QCD controls the matrix elements between hadron states.

**Calling the Fermi theory “nonrenormalizable” as if that meant useless.** Nonrenormalizable interactions are exactly what effective field theory expects. The question is not whether they are present; the question is what scale suppresses them and how accurate the expansion is.

## Relations to other pages

This page closes the Electroweak Theory chapter by connecting the $W$ and $Z$ interactions to the older low-energy language of weak decays.

The next chapter, [Higgs Sector](/gauge-theories-standard-model/higgs-sector/), explains the origin of the masses used here:

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{m_W}{c_W}.
$$

The Flavor and Neutrinos chapter later develops the CKM and PMNS matrices systematically. The Standard Model Architecture chapter assembles the gauge, Higgs, Yukawa, and anomaly-cancellation data into the full Standard Model Lagrangian. The Renormalization, RG, and EFT volume gives the broader effective-field-theory logic behind integrating out heavy particles.

## Research status

The tree-level Fermi limit is established textbook physics. It is the leading term in the low-energy expansion of the Standard Model after integrating out $W$ and $Z$ bosons.

Active work enters when this leading picture is embedded in precision physics: electroweak radiative corrections, hadronic and nuclear matrix elements, CKM unitarity tests, lepton-universality tests, neutrino scattering, and SMEFT fits. In those settings, the Fermi operator is the starting line, not the finish line.

## Exercises

### 1. Integrate out a complex massive vector at tree level

Start from

$$
\mathcal L
=
m^2W_\mu^+W^{-\mu}
-a(W_\mu^+J_+^\mu+W_\mu^-J_-^\mu),
$$

where $a$ is a constant. Ignore derivatives. Show that integrating out $W^\pm$ gives

$$
\mathcal L_{\rm eff}
=-\frac{a^2}{m^2}J_+^\mu J_{-\mu}.
$$

<details><summary><strong>Solution</strong></summary>

The algebraic equations of motion are

$$
m^2W_\mu^- = aJ_{+\mu},
\qquad
m^2W_\mu^+ = aJ_{-\mu}.
$$

Thus

$$
W_\mu^- = \frac{a}{m^2}J_{+\mu},
\qquad
W_\mu^+ = \frac{a}{m^2}J_{-\mu}.
$$

Substituting back,

$$
\mathcal L_{\rm eff}
=
\frac{a^2}{m^2}J_+\cdot J_-
-\frac{a^2}{m^2}J_-\cdot J_+
-\frac{a^2}{m^2}J_+\cdot J_-
=
-\frac{a^2}{m^2}J_+\cdot J_-.
$$

For $a=g/\sqrt2$ and $m=m_W$, this gives $-g^2J_+\cdot J_-/(2m_W^2)$.

</details>

### 2. Derive the relation between G_F and v

Use

$$
m_W=\frac{gv}{2}
$$

and the definition

$$
\frac{G_F}{\sqrt2}=\frac{g^2}{8m_W^2}
$$

to show that

$$
\frac{G_F}{\sqrt2}=\frac{1}{2v^2}.
$$

<details><summary><strong>Solution</strong></summary>

Since

$$
m_W^2=\frac{g^2v^2}{4},
$$

we have

$$
\frac{g^2}{8m_W^2}
=
\frac{g^2}{8(g^2v^2/4)}
=
\frac{1}{2v^2}.
$$

Therefore $G_F=1/(\sqrt2v^2)$, or $v=(\sqrt2G_F)^{-1/2}$ at tree level.

</details>

### 3. Track the factor of four in muon decay

Show that

$$
-\frac{4G_F}{\sqrt2}
(\bar\nu_{\mu L}\gamma^\mu\mu_L)
(\bar e_L\gamma_\mu\nu_{eL})
$$

is equal to

$$
-\frac{G_F}{\sqrt2}
(\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu)
(\bar e\gamma_\mu(1-\gamma^5)\nu_e).
$$

<details><summary><strong>Solution</strong></summary>

For left-handed fields,

$$
\bar\nu_{\mu L}\gamma^\mu\mu_L
=
\bar\nu_\mu\gamma^\mu P_L\mu
=
\frac12\bar\nu_\mu\gamma^\mu(1-\gamma^5)\mu.
$$

Similarly,

$$
\bar e_L\gamma_\mu\nu_{eL}
=
\frac12\bar e\gamma_\mu(1-\gamma^5)\nu_e.
$$

The product of the two left-handed bilinears is therefore $1/4$ times the product of the two $(1-\gamma^5)$ bilinears. The coefficient $4G_F/\sqrt2$ becomes $G_F/\sqrt2$.

</details>

### 4. Neutral-current matching

A real massive vector $Z_\mu$ has low-energy Lagrangian

$$
\mathcal L
=
\frac12m_Z^2Z_\mu Z^\mu-g_ZZ_\mu J^\mu.
$$

Show that integrating out $Z_\mu$ gives

$$
\mathcal L_{\rm eff}
=-\frac{g_Z^2}{2m_Z^2}J_\mu J^\mu.
$$

Then set $g_Z=g/c_W$ and $m_Z=gv/(2c_W)$.

<details><summary><strong>Solution</strong></summary>

The algebraic equation of motion is

$$
m_Z^2Z_\mu=g_ZJ_\mu,
$$

so

$$
Z_\mu=\frac{g_Z}{m_Z^2}J_\mu.
$$

Substitution gives

$$
\mathcal L_{\rm eff}
=
\frac12m_Z^2\frac{g_Z^2}{m_Z^4}J^2
-g_Z\frac{g_Z}{m_Z^2}J^2
=
-\frac{g_Z^2}{2m_Z^2}J^2.
$$

For $g_Z=g/c_W$ and $m_Z=gv/(2c_W)$,

$$
\frac{g_Z^2}{2m_Z^2}
=
\frac{g^2/c_W^2}{2g^2v^2/(4c_W^2)}
=
\frac{2}{v^2}
=
\frac{4G_F}{\sqrt2}.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§87–90, for the Standard Model gauge/Higgs sector and weak interactions of leptons and quarks.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 22 for the four-Fermi theory as an effective interaction and Ch. 29 for weak interactions.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory, low-energy weak interactions, and renormalization of gauge theories.
- Burgess, *Introduction to Effective Field Theory*, Chs. 7 and 9, for the Fermi theory and the Standard Model viewed as an effective field theory.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the conceptual role of gauge symmetry, massive vector bosons, and the Higgs phenomenon.

## Version history

- **2026-06-18:** Initial polished draft. Derived the charged-current and neutral-current Fermi limits, fixed the $G_F$ normalization, and added exercises on tree-level matching.
