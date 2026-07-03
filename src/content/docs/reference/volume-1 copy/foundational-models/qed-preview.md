---
title: "QED Preview"
description: "A foundation-level preview of spinor quantum electrodynamics: the Dirac field coupled to photons, Feynman rules, Ward identities, loops, infrared physics, and why full QED belongs in a later section."
sidebar:
  label: "QED Preview"
  order: 4
---

## Summary

**Quantum electrodynamics**, or QED, is the quantum field theory of charged spin-one-half matter coupled to the electromagnetic field. In its simplest one-fermion form,

$$
\boxed{
\mathcal L_\text{QED}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
}
$$

For the electron, qft.org writes $q=-e$ with $e>0$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

QED is the first physically central relativistic QFT most students meet. It contains the Dirac field, Maxwell gauge redundancy, photon polarizations, gauge fixing, Ward identities, loop renormalization, infrared subtleties, and some of the most precise predictions in all of physics. This page is only a **preview**. Its job is to show how the foundational machinery fits together before the later full QED section takes over.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Map of spinor QED](/figures/foundations/qed-preview-map.svg)

<figcaption>

Spinor QED couples the Dirac current to the photon. Gauge fixing gives a photon propagator, the covariant derivative gives the electron-photon vertex, Ward identities protect gauge invariance, and loops produce vacuum polarization, self-energy, and vertex corrections.

</figcaption>
</figure>

## Prerequisites

You should know [Dirac Field](/foundations/free-fields/dirac-field/), [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/), [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/), and [Scalar QED](/foundations/foundational-models/scalar-qed/).

:::note[Scope]
This page is not the full QED chapter. It does not compute the Lamb shift, anomalous magnetic moment, beta function, detailed cross sections, or infrared-safe inclusive rates. Those belong in **Gauge Theories and the Standard Model**, **Perturbative QFT and Scattering**, and **Renormalization, RG, and EFT**.
:::

## The Lagrangian

For a Dirac field of Abelian charge $q$,

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{+iq\alpha},
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

The covariant derivative

$$
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi
$$

transforms in the same way as $\psi$. Therefore

$$
\overline\psi i\gamma^\mu D_\mu\psi
$$

is gauge invariant.

The QED Lagrangian is

$$
\boxed{
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi.
}
$$

Expanding the covariant derivative gives

$$
\overline\psi i\gamma^\mu D_\mu\psi
=\overline\psi i\gamma^\mu\partial_\mu\psi
-qA_\mu\overline\psi\gamma^\mu\psi.
$$

Thus

$$
\mathcal L_\text{int}=-A_\mu j^\mu,
\qquad
\boxed{j^\mu=q\overline\psi\gamma^\mu\psi.}
$$

For the electron, $q=-e$, so the interaction term is

$$
\mathcal L_\text{int}=+eA_\mu\overline\psi_e\gamma^\mu\psi_e.
$$

Many textbooks absorb this sign differently and write the electron-photon vertex as $-ie\gamma^\mu$. With qft.org's charge convention, the general charge-$q$ vertex is the cleanest statement.

## Feynman rules at first pass

After covariant gauge fixing,

$$
\mathcal L_\text{gf}=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2,
$$

the photon propagator is

$$
D_{\mu\nu}(k)
=\frac{-i}{k^2+i\epsilon}
\left[g_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right].
$$

In Feynman gauge, $\xi=1$:

$$
D_{\mu\nu}(k)=\frac{-ig_{\mu\nu}}{k^2+i\epsilon}.
$$

The Dirac propagator is

$$
S_F(p)=\frac{i(\slashed p+m)}{p^2-m^2+i\epsilon}.
$$

The electron-photon vertex for a fermion of charge $q$ is

$$
\boxed{-iq\gamma^\mu.}
$$

For the electron, $q=-e$, so this is

$$
+ie\gamma^\mu
$$

in qft.org conventions. If you use the common convention $D_\mu=\partial_\mu+ieA_\mu$ for the electron field, the same physics is written with vertex $-ie\gamma^\mu$. Pick one convention and keep it nailed to the wall.

External photon states carry polarization vectors $\epsilon_\mu(k)$ satisfying, for physical transverse photons,

$$
k\cdot\epsilon(k)=0.
$$

Gauge invariance says more than transversality of external wavefunctions: physical amplitudes vanish when an external photon polarization is replaced by its momentum,

$$
\boxed{\mathcal M(\epsilon_\mu(k)\to k_\mu)=0.}
$$

That statement is the on-shell Ward identity.

## Why spinor QED is simpler and harder than scalar QED

Spinor QED is simpler than scalar QED in one diagrammatic respect: the Dirac kinetic term is first order in $D_\mu$, so minimal coupling produces only one photon field at the vertex. There is no minimal spinor-QED seagull term.

It is harder in another respect: every amplitude carries spinor wavefunctions, gamma matrices, spin sums, and closed-fermion-loop signs.

| Feature | Spinor QED |
|---|---|
| matter field | Dirac spinor $\psi$ |
| interaction | $-qA_\mu\overline\psi\gamma^\mu\psi$ |
| vertex | $-iq\gamma^\mu$ |
| matter propagator | $i(\slashed p+m)/(p^2-m^2+i\epsilon)$ |
| contact photon vertex | none from minimal Dirac coupling |
| essential identity | Ward–Takahashi identity |
| loop signatures | vacuum polarization, self-energy, vertex correction |

Tiny Lagrangian, enormous consequences. QED is annoyingly efficient that way.

## Tree-level processes

The same electron-photon vertex generates the classic tree-level processes:

| Process | Diagrammatic content | What it teaches |
|---|---|---|
| electron-muon scattering | one photon exchange | Coulomb interaction from photon exchange |
| Møller scattering | direct and exchange diagrams | identical fermions and exchange signs |
| Bhabha scattering | annihilation and scattering channels | crossing symmetry |
| Compton scattering | two electron-exchange diagrams | Ward identity for external photons |
| pair annihilation | $e^+e^-\to\gamma\gamma$ | antiparticles and crossing |

At low momentum transfer, one-photon exchange reproduces the Coulomb potential. In momentum space, the photon propagator contributes roughly $1/\mathbf q^2$ in the static limit, and Fourier transforming gives

$$
V(r)\propto \frac{q_1q_2}{4\pi r}.
$$

At high precision, the same theory produces radiative corrections to Coulomb's law, magnetic moments, atomic energy levels, and scattering amplitudes.

## Ward identities

The global current

$$
j^\mu=q\overline\psi\gamma^\mu\psi
$$

is conserved by the Dirac equation when the mass term respects the symmetry:

$$
\partial_\mu j^\mu=0.
$$

The local gauge symmetry upgrades this classical conservation law into quantum Ward identities. For time-ordered correlators, current conservation holds up to contact terms. For physical amplitudes, those contact terms do not spoil the on-shell transversality condition.

The off-shell Ward–Takahashi identity relates the exact photon-fermion vertex to the exact fermion propagator. Schematically,

$$
k_\mu\Gamma^\mu(p+k,p)
=q\left[S^{-1}(p+k)-S^{-1}(p)\right],
$$

up to sign conventions for $q$ and momentum flow.

This is a very strong constraint. In common renormalization schemes it implies the equality of the vertex and fermion wavefunction renormalization constants,

$$
Z_1=Z_2,
$$

again with the usual caveat that the precise definitions of $Z_1$ and $Z_2$ are scheme and convention dependent. The physical lesson is not the name of the constants; it is that gauge symmetry relates charge renormalization, field renormalization, and vertex corrections.

## Loop anatomy

At one loop, QED develops three classic corrections:

| Correction | Diagram | Physical meaning |
|---|---|---|
| vacuum polarization | fermion loop with two photon legs | charge screening and photon self-energy |
| electron self-energy | photon loop attached to an electron line | mass and field renormalization |
| vertex correction | photon loop correcting the electron-photon vertex | magnetic moment and charge form factor |

These diagrams are ultraviolet divergent before regularization. Gauge invariance controls the allowed counterterms:

$$
-\frac14Z_3F_{\mu\nu}F^{\mu\nu},
\qquad
Z_2\overline\psi i\slashed\partial\psi,
\qquad
-Z_m m\overline\psi\psi,
\qquad
\text{and the gauge-tied vertex term.}
$$

The finite part of the one-loop vertex correction includes the famous anomalous magnetic moment. The leading correction is often summarized as

$$
g_e=2\left(1+\frac{\alpha}{2\pi}+\cdots\right),
\qquad
\alpha=\frac{e^2}{4\pi}.
$$

This formula is far beyond the required machinery of this preview, but it explains why QED became the flagship example of perturbative QFT.

## Infrared physics

Photons are massless. That is wonderful for long-range electromagnetism and inconvenient for scattering theory.

Soft photons with very small energy can be emitted at arbitrarily low cost. Virtual soft photons also appear in loop corrections. As a result, amplitudes for processes with a fixed number of photons can contain infrared divergences.

The cure is not to pretend detectors resolve infinitely soft radiation. Physical cross sections are inclusive over unresolved soft photons. The cancellation between real and virtual soft effects is one of the major lessons of QED and belongs to the later infrared-physics pages.

For foundations, remember the slogan:

$$
\boxed{
\text{In QED, charged-particle scattering is inseparable from soft photons.}
}
$$

This is also why the notion of a bare isolated charged particle is more subtle in QED than in a massive scalar toy model.

## Gauge fixing and ghosts

The photon kinetic operator is not invertible until gauge redundancy is fixed. In covariant gauges, the path integral includes a gauge-fixing term. For Abelian QED, the Faddeev–Popov determinant is independent of $A_\mu$, so ghosts decouple.

This is why the elementary QED Feynman rules have no interacting ghost lines. Non-Abelian Yang–Mills theory is different: the ghost determinant depends on the gauge field, so ghosts become real perturbative bookkeeping fields with their own interactions.

BRST symmetry is still useful conceptually in QED, but the first dramatic need for interacting ghosts appears in non-Abelian gauge theory.

## QED as a model and as reality

QED is both a physical theory and a model.

As a physical theory, it accurately describes electrons, positrons, photons, and many electromagnetic processes at energies where weak, strong, gravitational, and compositeness effects can be neglected.

As a model, it teaches structural QFT lessons:

- local gauge redundancy,
- spinor Feynman rules,
- Ward identities,
- renormalization,
- running coupling,
- infrared divergences,
- inclusive observables,
- effective-field-theory interpretation.

At sufficiently high energies, QED is not isolated from the electroweak theory. In the Standard Model, electromagnetism is the unbroken low-energy remnant of electroweak gauge symmetry. QED also has a perturbative Landau-pole issue if extrapolated as a standalone theory to arbitrarily high energies. For qft.org, the right viewpoint is modern and modest: QED is a spectacularly successful effective quantum field theory.

## Common pitfalls

### Treating gauge invariance as optional bookkeeping

Gauge invariance is not just a way to simplify calculations. It removes unphysical photon polarizations, enforces Ward identities, and controls counterterms.

### Mixing charge-sign conventions

The electron charge is negative. qft.org writes $q_e=-e$ with $e>0$. A vertex sign that differs from a textbook is usually a convention difference, not new physics.

### Forgetting the closed-fermion-loop sign

Every closed fermion loop carries an extra minus sign from Grassmann statistics.

### Assuming every photon polarization is physical

Covariant gauges use extra components of $A_\mu$. Ward identities ensure that unphysical polarizations do not affect physical amplitudes.

### Ignoring soft photons

Because the photon is massless, exclusive fixed-photon-number scattering probabilities are not always physical infrared-finite observables. Inclusive observables are the right objects.

### Thinking QED is the whole electroweak theory

QED is the low-energy electromagnetic part. Weak interactions and electroweak symmetry breaking require a larger gauge theory.

## Relation to other topics

- [Dirac Field](/foundations/free-fields/dirac-field/) gives the spinor equation, spin sums, and free propagator.
- [Maxwell Field](/foundations/free-fields/maxwell-field/) explains photon degrees of freedom and gauge redundancy.
- [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) derives the covariant derivative and current coupling.
- [Scalar QED](/foundations/foundational-models/scalar-qed/) gives the spin-zero comparison and the seagull vertex.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) gives the operator and path-integral logic behind gauge-current identities.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) explains why photon propagators require a gauge choice.
- Perturbative QFT and Scattering will compute QED amplitudes, cross sections, and loop corrections.
- Renormalization/RG/EFT will treat charge renormalization, running coupling, and QED as an effective theory.
- Gauge Theories and the Standard Model will place QED inside electroweak theory.

## Research status

Perturbative QED, Ward identities, one-loop renormalization, and infrared cancellation are textbook-standard. QED is among the best-tested effective field theories in physics. As a standalone theory extrapolated to arbitrarily high energies, it is not usually regarded as a complete fundamental theory; in nature it is embedded in the electroweak Standard Model.

## Exercises

### Exercise 1: Gauge invariance of the Dirac term

Show that

$$
\overline\psi i\gamma^\mu D_\mu\psi
$$

is invariant under

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto\overline\psi e^{+iq\alpha},
\qquad
D_\mu\psi\mapsto e^{-iq\alpha}D_\mu\psi.
$$

<details>
<summary><strong>Solution</strong></summary>

The transformed term is

$$
\overline\psi e^{+iq\alpha} i\gamma^\mu e^{-iq\alpha}D_\mu\psi.
$$

The phase is an ordinary scalar in spinor space, so it commutes with $\gamma^\mu$ and cancels:

$$
\overline\psi i\gamma^\mu D_\mu\psi.
$$

</details>

### Exercise 2: Vertex factor for charge q

Starting from

$$
\mathcal L_\text{int}=-qA_\mu\overline\psi\gamma^\mu\psi,
$$

find the electron-photon vertex for a Dirac fermion of charge $q$.

<details>
<summary><strong>Solution</strong></summary>

The Dyson expansion contains

$$
i\int d^4x\,\mathcal L_\text{int}
=-iq\int d^4x\,A_\mu\overline\psi\gamma^\mu\psi.
$$

The local vertex factor is therefore

$$
\boxed{-iq\gamma^\mu.}
$$

For an electron, $q=-e$, so this becomes $+ie\gamma^\mu$ in qft.org's convention.

</details>

### Exercise 3: Current conservation

Use the free Dirac equations

$$
(i\slashed\partial-m)\psi=0,
\qquad
\partial_\mu\overline\psi\,i\gamma^\mu + m\overline\psi=0
$$

to show that $j^\mu=q\overline\psi\gamma^\mu\psi$ is conserved.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu
=q(\partial_\mu\overline\psi)\gamma^\mu\psi
+q\overline\psi\gamma^\mu\partial_\mu\psi.
$$

From the adjoint Dirac equation,

$$
(\partial_\mu\overline\psi)\gamma^\mu=im\overline\psi.
$$

From the Dirac equation,

$$
\gamma^\mu\partial_\mu\psi=-im\psi.
$$

Thus

$$
\partial_\mu j^\mu=q(im\overline\psi\psi-im\overline\psi\psi)=0.
$$

</details>

### Exercise 4: No seagull from the Dirac term

Explain why the minimally coupled Dirac Lagrangian contains no two-photon contact vertex.

<details>
<summary><strong>Solution</strong></summary>

The Dirac kinetic term is linear in the covariant derivative:

$$
\overline\psi i\gamma^\mu D_\mu\psi
=\overline\psi i\gamma^\mu\partial_\mu\psi
-qA_\mu\overline\psi\gamma^\mu\psi.
$$

Only one power of $A_\mu$ appears. In scalar QED, the kinetic term is quadratic in $D_\mu$:

$$
(D_\mu\Phi)^\dagger D^\mu\Phi,
$$

so it contains both one-photon and two-photon scalar vertices.

</details>

### Exercise 5: Coulomb potential from photon exchange

In the static limit, use

$$
\int\frac{d^3\mathbf q}{(2\pi)^3}
\frac{e^{i\mathbf q\cdot\mathbf r}}{\mathbf q^2}
=\frac{1}{4\pi r}
$$

to explain why massless photon exchange gives a long-range force.

<details>
<summary><strong>Solution</strong></summary>

The static photon propagator contributes a factor proportional to $1/\mathbf q^2$. Fourier transforming to position space gives

$$
V(r)\propto \frac{q_1q_2}{4\pi r}.
$$

There is no exponential decay because the photon is massless. A massive exchanged particle would instead produce a Yukawa factor $e^{-Mr}$.

</details>

### Exercise 6: Ward identity and external photons

State the on-shell Ward identity for an amplitude with one external photon and explain its physical meaning.

<details>
<summary><strong>Solution</strong></summary>

The identity is

$$
\mathcal M(\epsilon_\mu(k)\to k_\mu)=0.
$$

It means that the longitudinal pure-gauge part of the external photon polarization does not affect a physical amplitude. Equivalently, physical amplitudes depend only on the gauge-invariant transverse photon polarizations.

</details>

## Sources and further reading

- Mark Srednicki, *Quantum Field Theory*, §§58–68, for spinor electrodynamics, scalar electrodynamics, QED loop corrections, vertex functions, magnetic moments, and Ward identities.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 27, 30–35, for minimal coupling, QED Feynman rules, Faddeev–Popov quantization, QED renormalization, Coulomb's law, and anomalous magnetic moments.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 8, 10–13, for electrodynamics, Ward identities, Källén–Lehmann structure, one-loop QED, renormalization, and infrared effects.
- Julian Schwinger, “On Quantum-Electrodynamics and the Magnetic Moment of the Electron,” *Physical Review* **73** (1948), 416–417, for the classic one-loop anomalous-magnetic-moment result.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 5–7 and 9–10, for practical QED Feynman rules, tree amplitudes, loops, and Ward identities.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, Parts II–III, for a compact conceptual route through Dirac fields, gauge invariance, QED diagrams, renormalization, and magnetic moments.

## Version history

- **2026-05-24:** Initial qft.org QED preview page: spinor QED Lagrangian, charge conventions, Feynman rules, Ward identities, loop anatomy, infrared caveats, relation to scalar QED, common pitfalls, and exercises.
