---
title: "Theta Terms"
description: "Explains theta terms as phases assigned to quantized topological sectors, with Yang–Mills, sigma-model, electromagnetic, instanton, periodicity, and CP examples."
sidebar:
  label: "Theta Terms"
  order: 1
level: Advanced
status: "Polished draft"
source: "Srednicki §§93–94; Coleman, The Uses of Instantons; Polyakov, Gauge Fields and Strings; Zee; Altland–Simons Ch. 8; standard instanton and topological-response references."
topics:
  - theta terms
  - theta vacua
  - instanton number
  - topological charge
  - Yang Mills theory
  - sigma models
  - CP violation
  - Witten effect
canonicalTopics:
  - theta-terms
  - theta-vacua
  - yang-mills-theta-angle
  - instanton-number
  - topological-susceptibility
researchStatus:
  established:
    - 'A theta term weights quantized topological sectors by a phase $e^{i\theta Q}$ and can change the quantum theory even when its local density is a total derivative.'
    - 'In four-dimensional Yang–Mills theory, the theta angle is periodic when the instanton number is integral, and orientation-reversing symmetries can be preserved only at special values such as $\theta=0$ and $\theta=\pi$, subject to global caveats.'
  active:
    - 'The detailed behavior at special theta angles, especially $\theta=\pi$, remains an active nonperturbative subject in gauge theories, sigma models, theories with higher-form symmetries, and topological phases.'
---

## Summary

A theta term is a topological term of the form

$$
S_\theta=\theta Q,
$$

where $Q$ is a quantized topological charge. In Lorentzian signature it contributes the phase

$$
e^{iS_\theta}=e^{i\theta Q}.
$$

In Euclidean path-integral language, the same statement is usually written as

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

This one line is the heart of the subject. The local equations of motion may not notice $\theta$, but the quantum path integral does, because it sums over sectors with different $Q$.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing theta terms as phases assigned to integer topological sectors, with theta periodicity and CP or time-reversal reflection mapping Q to minus Q.](/figures/symmetry-anomalies-topology/theta-term-sector-sum.svg)

<figcaption>

A theta term assigns the phase $e^{i\theta Q}$ to the sector of topological charge $Q$. Periodicity follows from $Q\in\mathbb Z$. Orientation reversal sends $Q\mapsto -Q$, so a CP or time-reversal symmetry can survive only when $\theta\equiv-\theta$ modulo the periodicity.

</figcaption>
</figure>

The most famous example is four-dimensional Yang–Mills theory,

$$
Q=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F),
$$

where $Q$ is the instanton number on a closed Euclidean four-manifold. But theta terms are much broader: they appear for quantum rotors, nonlinear sigma models, compact electrodynamics, QCD, axion effective theories, and topological response actions.

## Prerequisites

Read [Conventions and Notation](/symmetry-anomalies-topology/conventions/) for the differential-form convention

$$
F=dA-iA\wedge A,
$$

and the normalization

$$
\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

for an $SU(N)$ bundle on a closed oriented four-manifold with the standard fundamental trace normalization.

The most useful conceptual prerequisites are [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/), [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), and [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/).

You should also be comfortable with Euclidean path integrals, compact gauge fields, Stokes’ theorem, and the idea that a field configuration may carry an integer winding number or instanton number.

## Core idea

A theta term is the simplest way a QFT can remember the topology of field space. Suppose the configuration space decomposes into sectors labeled by an integer

$$
Q[\Phi]\in\mathbb Z.
$$

The ordinary action $S_0$ may be unable to distinguish two sectors by any local perturbative expansion around $Q=0$. The theta term distinguishes them by a phase:

$$
S[\Phi]=S_0[\Phi]+\theta Q[\Phi].
$$

Therefore

$$
Z(\theta)=\sum_{Q\in\mathbb Z}\int_{Q}\mathcal D\Phi\,e^{iS_0[\Phi]}e^{i\theta Q}
$$

in Lorentzian notation, or

$$
Z_E(\theta)=\sum_{Q\in\mathbb Z}\int_{Q}\mathcal D\Phi\,e^{-S_{E,0}[\Phi]}e^{i\theta Q}
$$

in Euclidean notation.

The periodicity is immediate:

$$
Z(\theta+2\pi)=Z(\theta),
$$

provided every allowed sector has integer $Q$ and no extra background structure fractionalizes the charge.

That last clause is not a footnote. It is where many modern subtleties live. The periodicity of a theta parameter depends on the allowed bundles, the global form of the gauge group, background fields for higher-form symmetries, and whether the theory is bosonic or requires spin data.

## Setup and conventions

This page uses the convention fixed in the volume overview:

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

For non-Abelian gauge fields, $A=A^aT^a$ with Hermitian generators and

$$
\operatorname{tr}_{\square}(T^aT^b)=\frac12\delta^{ab}.
$$

The Yang–Mills instanton number is

$$
Q=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F).
$$

In components this is

$$
Q=\frac{1}{32\pi^2}\int_{X_4}d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu},
$$

where

$$
\widetilde F^{a\mu\nu}=\frac12\varepsilon^{\mu\nu\rho\sigma}F^a_{\rho\sigma}
$$

in Euclidean orientation conventions. A reversal of orientation flips the sign of $Q$.

:::note[Convention-sensitive source note]
Some gauge-theory texts put the coupling $g$ inside the field strength and write the theta density as $g^2\theta F^a_{\mu\nu}\widetilde F^{a\mu\nu}/(32\pi^2)$. This page absorbs the normalization into the connection used to define $F$ and fixes the term by the integer formula $Q=(8\pi^2)^{-1}\int\operatorname{tr}(F\wedge F)$. Compare phases $e^{i\theta Q}$ rather than isolated component densities.
:::

For a Lorentzian theory, we write

$$
S_\theta=\theta Q.
$$

For a Euclidean path integral, the same theta term appears as the phase

$$
e^{-S_E}\supset e^{i\theta Q}.
$$

Thus it is common to say that the Euclidean action contains

$$
S_{E,\theta}=-i\theta Q.
$$

This imaginary Euclidean term is exactly why theta terms can produce sign problems in numerical simulations.

## Total derivative does not mean zero

For Yang–Mills theory,

$$
\operatorname{tr}(F\wedge F)=d\operatorname{CS}_3(A),
$$

where, in the Hermitian-generator convention,

$$
\operatorname{CS}_3(A)
=
\operatorname{tr}\left(A\wedge dA-\frac{2i}{3}A\wedge A\wedge A\right).
$$

This equation is true locally. It explains why the theta density does not change the local classical Yang–Mills equation on a closed spacetime when $\theta$ is constant.

But locally exact does not mean globally irrelevant. There are three reasons.

First, $A$ may not be globally defined as a single smooth one-form. Gauge bundles are described by patches and transition functions. The local Chern–Simons forms on patches can glue into a globally nonzero integer characteristic class.

Second, even when $F=0$ at spatial infinity, large gauge transformations can label distinct classical vacua. Tunneling between them is controlled by instantons, and the theta term changes the tunneling phase.

Third, if spacetime has a boundary, Stokes’ theorem gives

$$
\int_{X_4}\operatorname{tr}(F\wedge F)=\int_{\partial X_4}\operatorname{CS}_3(A),
$$

modulo patching subtleties. The boundary Chern–Simons term is then physical unless it is canceled by boundary degrees of freedom or by a boundary condition.

So the safe slogan is:

$$
\text{total derivative locally}\not\Rightarrow\text{irrelevant globally}.
$$

## Yang–Mills theta angle

For pure $SU(N)$ Yang–Mills theory on a closed Euclidean four-manifold, the action with theta angle is

$$
S_E
=
\frac{1}{2g^2}\int_{X_4}\operatorname{tr}(F\wedge\star F)
-i\theta\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F).
$$

The partition function decomposes as

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q,
$$

where $Z_Q$ denotes the path integral restricted to instanton number $Q$.

The $2\pi$ periodicity follows from $Q\in\mathbb Z$:

$$
\theta\sim\theta+2\pi.
$$

In weakly coupled semiclassical language, instantons with $Q=+1$ and antiinstantons with $Q=-1$ contribute phases $e^{+i\theta}$ and $e^{-i\theta}$. This produces a theta-dependent vacuum energy. In a dilute-instanton approximation one often finds a leading dependence of the schematic form

$$
E(\theta)-E(0)\propto 1-\cos\theta,
$$

but this formula is not a general theorem of strongly coupled Yang–Mills theory. What is robust is periodicity and the symmetry constraint under orientation reversal.

## Theta vacua

There is another, Hamiltonian way to see the same parameter. Work in temporal gauge in pure Yang–Mills theory. Classical zero-energy gauge fields are pure gauge,

$$
A_i=i\,U\partial_iU^{-1},
$$

up to convention-dependent factors. If space is compactified by a point at infinity, a gauge transformation $U(\mathbf x)$ defines a map

$$
S^3_{\rm space}\longrightarrow G.
$$

For $G=SU(N)$ with $N\geq2$,

$$
\pi_3(SU(N))\cong\mathbb Z.
$$

Thus classical vacua can be labeled by an integer $n$. Large gauge transformations shift $n$:

$$
|n\rangle\longmapsto |n+k\rangle.
$$

The Hamiltonian is invariant under this shift, so its eigenstates are Bloch-wave-like superpositions,

$$
|\theta\rangle=\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

A large gauge transformation of winding $k$ acts by

$$
U_k|\theta\rangle=e^{ik\theta}|\theta\rangle.
$$

The theta angle is therefore both a coefficient in the Lagrangian and a label of the representation of large gauge transformations on the vacuum sector. These are two descriptions of the same physics.

:::note[Source note]
Coleman and Srednicki both present the theta-vacuum picture as a Bloch-wave superposition over winding-number vacua. The overall sign in $|\theta\rangle=\sum_n e^{-in\theta}|n\rangle$ depends on whether the large gauge transformation is defined to send $n\mapsto n+k$ or $n\mapsto n-k$.
:::

## Orientation reversal, CP, and special theta values

A theta term is often odd under orientation reversal. In four-dimensional Yang–Mills theory, parity, time reversal, or CP sends

$$
Q\longmapsto -Q.
$$

Therefore

$$
S_\theta=\theta Q
\longmapsto
-\theta Q.
$$

If the theory has periodicity $\theta\sim\theta+2\pi$, then an orientation-reversing symmetry can be present only when

$$
\theta\equiv-\theta\pmod{2\pi}.
$$

This gives

$$
\theta=0,\pi\pmod{2\pi}.
$$

The point $\theta=0$ is the ordinary CP-preserving point. The point $\theta=\pi$ is special because it is also invariant modulo periodicity. Special does not mean trivial. In many theories, $\theta=\pi$ is precisely where mixed anomalies, spontaneous CP breaking, domain walls, or nontrivial topological order can appear.

This simple observation is one of the great theta-term lessons:

$$
\theta=\pi\quad\text{is often a symmetry-enhanced and constraint-rich point.}
$$

## Sigma-model theta terms

Theta terms are not exclusive to gauge theory. Let

$$
\mathbf n(x)\in S^2,
\qquad
\mathbf n\cdot\mathbf n=1,
$$

be the field of the two-dimensional $O(3)$ nonlinear sigma model on a closed oriented Euclidean surface $\Sigma_2$. The topological charge is the winding number

$$
Q[\mathbf n]
=
\frac{1}{4\pi}\int_{\Sigma_2}
\mathbf n\cdot(\partial_1\mathbf n\times\partial_2\mathbf n)\,d^2x
\in\mathbb Z.
$$

The Euclidean path integral can include

$$
e^{i\theta Q[\mathbf n]}.
$$

Again $\theta\sim\theta+2\pi$. Again orientation reversal sends $Q\mapsto -Q$. Again $\theta=0$ and $\theta=\pi$ are special.

This example is important because it appears in statistical physics, spin chains, and low-dimensional QFT. It also teaches a healthy caution: the same formal theta-term structure can lead to very different infrared behavior depending on dimension, target-space topology, symmetries, and microscopic realization.

For a general sigma model with target space $\mathcal M$, theta-like terms often arise from cohomology classes. A closed $d$-form $\omega_d$ on $\mathcal M$ can define

$$
S_\theta=\theta\int_{\Sigma_d}\phi^*\omega_d,
$$

where $\phi:\Sigma_d\to\mathcal M$. Quantization of periods of $\omega_d$ determines the periodicity of $\theta$.

## Compact electrodynamics and the electromagnetic theta term

For a compact $U(1)$ gauge field in four dimensions, one can write

$$
S_\theta=\frac{\theta}{8\pi^2}\int_{X_4}F\wedge F.
$$

This is the topological response term of axion electrodynamics. Locally it is proportional to $\mathbf E\cdot\mathbf B$ in Lorentzian signature. Globally its normalization depends on flux quantization:

$$
\frac{1}{2\pi}\int_{\Sigma_2}F\in\mathbb Z.
$$

The integral

$$
\frac{1}{8\pi^2}\int F\wedge F
=
\frac12\int c_1\smile c_1
$$

can depend on whether the four-manifold is spin and on how the electromagnetic field is coupled to fermions. On spin manifolds, the usual fermionic electromagnetic theta angle has $2\pi$ periodicity. On more general bosonic backgrounds, the naive periodicity can be different unless extra structure is specified.

:::caution[Periodicity depends on global data]
For non-Abelian $SU(N)$ bundles on closed four-manifolds, the instanton number above is integral. For $U(1)$ gauge fields, quotient gauge groups, or backgrounds for one-form symmetries, fractional topological charges can appear. Then $\theta\sim\theta+2\pi$ may be enlarged, reduced, or tied to shifts of other discrete counterterms. Never quote theta periodicity without saying which bundles and backgrounds are allowed.
:::

The electromagnetic theta term also leads to the Witten effect: in the presence of magnetic monopoles, the theta angle shifts the electric charge of a monopole. In a common normalization, a monopole of magnetic charge $m$ carries electric charge shifted by

$$
q_e \sim n+\frac{\theta}{2\pi}m,
\qquad n,m\in\mathbb Z,
$$

up to the chosen electric charge unit. The detailed derivation belongs to the later Witten Effect preview page.

## Theta and fermion phases in QCD

In QCD, the Yang–Mills theta angle is entangled with phases of the quark mass matrix. For $N_f$ quark flavors, write the mass term schematically as

$$
\mathcal L_m=-\bar q_R M q_L-\bar q_LM^\dagger q_R.
$$

An anomalous axial rotation changes the theta angle and the phase of $\det M$ together. The physical CP-violating parameter is a convention-dependent invariant combination, commonly written

$$
\bar\theta=\theta+\arg\det M.
$$

If one quark were exactly massless, an axial rotation could remove $\bar\theta$, making the theta angle unobservable. With all quarks massive, $\bar\theta$ is physical.

:::note[Convention-sensitive source note]
The sign in $\bar\theta=\theta+\arg\det M$ depends on the definition of the chiral rotation, the mass term, and the sign of the anomaly equation. Some references write the invariant as $\arg\det M-\theta$. The invariant statement is that only the anomalous-rotation-invariant combination of $\theta$ and the mass-matrix phase is observable.
:::

The small observed bound on strong CP violation is the strong CP problem: QCD permits a dimensionless CP-violating parameter, but experiments require it to be extremely small. The axion mechanism promotes $\bar\theta$ to a dynamical field whose potential is minimized near a CP-preserving value.

This page is not the place for a full phenomenological axion review. What matters here is the structural point: theta angles can mix with phases of fermion masses because anomalous transformations shift theta terms.

## Topological susceptibility

Theta dependence can be measured by differentiating the vacuum energy. In Euclidean finite volume $V_E$, define

$$
E(\theta)=-\frac{1}{V_E}\log Z(\theta)
$$

up to the usual infinite-volume limit and subtraction conventions. The topological susceptibility is

$$
\chi_t
=
\left.\frac{\partial^2E(\theta)}{\partial\theta^2}\right|_{\theta=0}.
$$

Using

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
$$

one finds, when $\langle Q\rangle_{\theta=0}=0$,

$$
\chi_t=\frac{1}{V_E}\langle Q^2\rangle_{\theta=0}.
$$

This formula makes the physics concrete. The theta term couples to the topological-charge distribution. If the theory has large fluctuations of $Q$, the vacuum energy is sensitive to theta. If the topological sectors decouple or cancel, theta dependence can vanish.

In QCD, topological susceptibility is tied to the anomalous axial symmetry, the eta-prime mass, and the axion potential. Those applications belong to the anomaly and model-calculation pages, but the definition begins here.

## Axion fields as dynamical theta angles

A constant theta angle can be replaced by a compact scalar field $a(x)$:

$$
\theta\longrightarrow \frac{a(x)}{f_a}.
$$

Then

$$
S_a\supset \frac{1}{8\pi^2}\int \frac{a}{f_a}\operatorname{tr}(F\wedge F).
$$

If $a$ has a periodicity

$$
a\sim a+2\pi f_a,
$$

then the axion coupling respects the same topological quantization as the theta angle. The shift symmetry of $a$ is exact perturbatively and broken nonperturbatively by sectors with nonzero $Q$.

This is a useful EFT pattern: a theta parameter is a background zero-form field; an axion is a dynamical version of that background.

## Common pitfalls

**Treating theta as visible in every Feynman diagram.** Around the trivial sector in flat perturbation theory, a constant Yang–Mills theta term does not modify ordinary perturbative vertices. Its effects are nonperturbative, boundary-sensitive, or tied to nontrivial backgrounds.

**Forgetting the Euclidean phase.** In Euclidean signature the theta term contributes $e^{i\theta Q}$, not $e^{-\theta Q}$. This is why the Euclidean action is complex when $\theta$ is real.

**Assuming $2\pi$ periodicity without checking $Q$.** The formula $\theta\sim\theta+2\pi$ assumes $Q\in\mathbb Z$. With quotient gauge groups, one-form backgrounds, non-spin manifolds, or fractional instantons, the periodicity can change.

**Confusing theta with an ordinary coupling.** Theta is dimensionless and periodic. It labels a compact parameter space, not a line.

**Saying CP is always broken at nonzero theta.** CP sends $\theta\mapsto-\theta$. Therefore CP is generically broken at nonzero theta, but $\theta=\pi$ can be CP invariant modulo periodicity. What happens there is dynamical and can be subtle.

**Ignoring boundaries.** Since many theta densities are locally total derivatives, boundaries convert them into lower-dimensional terms. Boundary conditions and boundary degrees of freedom must be specified.

**Mixing conventions for $F\widetilde F$.** Component formulas depend on Euclidean versus Lorentzian signature, orientation, generator normalization, and whether the gauge coupling is included in $F$. The invariant definition is the integral of $\operatorname{tr}(F\wedge F)$ with stated normalization.

## Relations to other pages

- [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/) explains the local-versus-global logic more systematically.
- [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) develops theta periodicity and its refinements by global form and background fields.
- [Witten Effect: Preview](/symmetry-anomalies-topology/topological-terms/witten-effect-preview/) explains the monopole charge shift caused by the electromagnetic theta term.
- [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) will develop the topological classification of Yang–Mills sectors.
- [Theta Vacua: Preview](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/theta-vacua-preview/) will return to the Hamiltonian construction of $|\theta\rangle$ states.
- [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) and [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) explain how theta terms interact with anomalous symmetry realization.

## Research status

The basic definition of theta terms, instanton number, theta vacua, and QCD theta dependence is standard. The main dangers are convention errors and overinterpreting semiclassical formulas in strongly coupled regimes.

Several theta-angle questions remain active because they are nonperturbative. Examples include Yang–Mills dynamics at $\theta=\pi$, mixed anomalies involving CP and center symmetry, theta dependence at large $N$, theta angles in chiral gauge theories, theta terms coupled to higher-form backgrounds, and spin-structure refinements of electromagnetic response.

The modern viewpoint treats theta terms not only as old instanton parameters, but also as background response terms and elements of the same global-data package as anomalies, invertible phases, and symmetry TFT.

## Exercises

### Exercise 1: Periodicity from sector decomposition

Suppose

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Show that $Z(\theta+2\pi)=Z(\theta)$. What changes if $Q$ can take values in $\frac{1}{N}\mathbb Z$?

<details><summary><strong>Solution</strong></summary>

For integer $Q$,

$$
e^{i(\theta+2\pi)Q}=e^{i\theta Q}e^{2\pi iQ}=e^{i\theta Q}.
$$

Therefore every term in the sum is unchanged and

$$
Z(\theta+2\pi)=Z(\theta).
$$

If $Q$ can take values in $\frac{1}{N}\mathbb Z$, then $e^{2\pi iQ}$ is not always equal to one. A shift by $2\pi N$ is always invisible:

$$
e^{i(\theta+2\pi N)Q}=e^{i\theta Q}e^{2\pi iNQ}=e^{i\theta Q}.
$$

The actual periodicity may be $2\pi N$ or may involve a simultaneous shift of a discrete counterterm, depending on the background fields and global structure.

</details>

### Exercise 2: CP-invariant theta values

Assume $Q\mapsto -Q$ under CP and $\theta\sim\theta+2\pi$. Find the theta values at which the theta term is CP invariant.

<details><summary><strong>Solution</strong></summary>

Under CP,

$$
e^{i\theta Q}\longmapsto e^{-i\theta Q}.
$$

The theory is CP invariant if this is equivalent to the original phase for every allowed integer $Q$. This requires

$$
\theta\equiv-\theta\pmod{2\pi}.
$$

Therefore

$$
2\theta\equiv0\pmod{2\pi},
$$

so

$$
\theta=0,\pi\pmod{2\pi}.
$$

The conclusion is kinematic. It does not decide whether CP is spontaneously broken at $\theta=\pi$; that is a dynamical question.

</details>

### Exercise 3: Yang–Mills theta term as a boundary term locally

Using

$$
\operatorname{tr}(F\wedge F)=d\operatorname{CS}_3(A),
$$

show why a constant theta term does not change local Yang–Mills equations on a closed spacetime, but can induce a boundary Chern–Simons term when $X_4$ has boundary.

<details><summary><strong>Solution</strong></summary>

The theta contribution is

$$
S_\theta=\frac{\theta}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F)
=
\frac{\theta}{8\pi^2}\int_{X_4}d\operatorname{CS}_3(A).
$$

On a closed manifold and within a single smooth topologically trivial patch, its variation is a total derivative, so it does not contribute to the bulk Euler–Lagrange equation.

If $X_4$ has boundary, Stokes’ theorem gives

$$
S_\theta=\frac{\theta}{8\pi^2}\int_{\partial X_4}\operatorname{CS}_3(A),
$$

again modulo patching subtleties. Thus the same local total derivative becomes a three-dimensional boundary term. Gauge invariance of the combined bulk-boundary system may then require boundary degrees of freedom, boundary conditions, or quantization constraints.

</details>

### Exercise 4: Topological susceptibility

Let

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q,
\qquad
E(\theta)=-\frac{1}{V_E}\log Z(\theta).
$$

Assume $\langle Q\rangle_{\theta=0}=0$. Show that

$$
\chi_t=\left.\frac{\partial^2E}{\partial\theta^2}\right|_{\theta=0}
=\frac{1}{V_E}\langle Q^2\rangle_{\theta=0}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{\partial\log Z}{\partial\theta}=i\langle Q\rangle_\theta.
$$

Differentiate once more:

$$
\frac{\partial^2\log Z}{\partial\theta^2}
=-\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

Since

$$
E(\theta)=-\frac{1}{V_E}\log Z(\theta),
$$

we get

$$
\frac{\partial^2E}{\partial\theta^2}
=\frac{1}{V_E}\left(\langle Q^2\rangle_\theta-\langle Q\rangle_\theta^2\right).
$$

At $\theta=0$, the assumption $\langle Q\rangle=0$ gives

$$
\chi_t=\frac{1}{V_E}\langle Q^2\rangle_{\theta=0}.
$$

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, “The Uses of Instantons,” for theta vacua and tunneling intuition.
- Mark Srednicki, *Quantum Field Theory*, §§93–94, for instantons, theta vacua, and quark-mass dependence of theta.
- A. M. Polyakov, *Gauge Fields and Strings*, for topology of gauge fields and instanton effects.
- A. Zee, *Quantum Field Theory in a Nutshell*, for monopoles, sigma-model topology, chiral anomalies, and physically motivated theta-term examples.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for theta terms and related topological terms in matter-oriented field theory.
- Edward Witten, “Dyons of Charge $e\theta/2\pi$,” *Physics Letters B* **86** (1979), for the Witten effect.
- Edward Witten, “Theta dependence in the large $N$ limit of four-dimensional gauge theories,” *Physical Review Letters* **81** (1998), for large-$N$ theta-dependence perspective.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
