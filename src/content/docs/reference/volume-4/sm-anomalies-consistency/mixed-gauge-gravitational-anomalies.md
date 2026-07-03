---
title: "Mixed Gauge–Gravitational Anomalies"
description: "Explains the mixed gravitational–hypercharge anomaly, the Standard Model trace-Y cancellation, and why gauging U(1) symmetries requires more than ordinary gauge-triangle checks."
sidebar:
  label: "Mixed Gauge–Gravitational Anomalies"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77 and §§87–91; Schwartz Ch. 30; Burgess Ch. 9; Weinberg Vol. II anomaly and Standard Model material."
topics:
  - mixed gauge-gravitational anomaly
  - hypercharge
  - Standard Model anomaly cancellation
  - chiral fermions
  - curved spacetime background
  - B minus L
canonicalTopics:
  - mixed-gauge-gravitational-anomaly
  - gravitational-hypercharge-anomaly
  - standard-model-anomaly-cancellation
  - trace-y-condition
  - gauged-b-minus-l
researchStatus:
  established:
    - "The Standard Model hypercharge current has vanishing mixed gauge–gravitational anomaly generation by generation."
  active:
    - "Modern anomaly analysis treats mixed gauge–gravity constraints together with global anomalies, anomaly inflow, and possible generalized symmetry constraints on extensions of the Standard Model."
---

## Summary

A mixed gauge–gravitational anomaly is what happens when a gauge current that looks conserved in flat spacetime fails to remain gauge-consistent in a curved background. In four-dimensional Standard Model applications, the most important local example is the mixed anomaly with one $U(1)$ gauge current and two insertions of the stress tensor. For a $U(1)$ current with charges $q_\psi$ carried by left-handed Weyl fermions, the coefficient is proportional to

$$
\operatorname{Tr} q
=\sum_{\psi_L} q_\psi\,d_{\rm spectator}(\psi).
$$

For hypercharge, the one-generation Standard Model gives

$$
\operatorname{Tr}Y
=6\left(\frac{1}{6}\right)
+3\left(-\frac{2}{3}\right)
+3\left(\frac{1}{3}\right)
+2\left(-\frac{1}{2}\right)
+1
=0.
$$

This is why the $U(1)_Y$ gauge symmetry remains consistent even when the Standard Model is coupled to background geometry.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Mixed gravitational hypercharge anomaly ledger](/figures/gauge-theories-standard-model/mixed-gravitational-hypercharge-ledger.svg)

<figcaption>

The mixed gravitational–hypercharge anomaly is governed by the linear trace of hypercharge over all left-handed Weyl components. Non-Abelian gauge factors do not give analogous local mixed gravitational anomalies in four dimensions because their generators are traceless, but a gauged $U(1)$ must pass the $\operatorname{Tr}q=0$ test.

</figcaption>
</figure>

This page explains why the apparently humble equation $\operatorname{Tr}Y=0$ is a real quantum consistency condition, not a decorative companion to the cubic $\operatorname{Tr}Y^3=0$ equation.

## Prerequisites

You should first read [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/), [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/), and [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/). You should be comfortable with the all-left-handed Standard Model fermion ledger and with the distinction between gauge symmetries and global symmetries.

We work in four spacetime dimensions. The phrase “mixed gauge–gravitational anomaly” here means a gauge anomaly whose coefficient is detected in a curved background. It is not the same as a pure gravitational anomaly in the diffeomorphism current. Pure local gravitational anomalies occur in dimensions $4k+2$, not in four-dimensional chiral gauge theories of the Standard Model type.

## The anomaly being tested

A chiral fermion path integral can fail to be invariant under a gauge transformation. For an Abelian gauge symmetry, the divergence of the gauge current can contain not only gauge-field terms such as $F\widetilde F$, but also a curvature term of the schematic form

$$
\nabla_\mu J_q^\mu
\supset
C_{qgg}\,R\widetilde R.
$$

Here $R\widetilde R$ denotes the gravitational Pontryagin density,

$$
R\widetilde R
\sim
\epsilon^{\mu\nu\rho\sigma}
R_{\mu\nu\alpha\beta}R_{\rho\sigma}{}^{\alpha\beta},
$$

up to normalization conventions. The coefficient is proportional to

$$
C_{qgg}=\sum_{\psi_L} q_\psi\,d_{\rm spectator}(\psi),
$$

where $d_{\rm spectator}(\psi)$ is the product of dimensions under gauge groups not appearing in the current insertion. For a Standard Model fermion, this means counting color and weak components.

If $q$ is the charge of a global current, a nonzero $C_{qgg}$ says the global current is anomalous in curved spacetime. That can be a physical statement. If $q$ is a dynamical gauge charge, a nonzero $C_{qgg}$ is fatal: gauge redundancy would fail in a gravitational background.

For hypercharge, therefore, the Standard Model must satisfy

$$
\operatorname{Tr}Y=0.
$$

## Why non-Abelian groups do not appear this way

Why is the mixed gravitational test usually discussed for $U(1)$ gauge factors? Because the gauge-current insertion contributes a trace over the gauge generator. For a non-Abelian group generator $T^a$ in any finite-dimensional representation of a semisimple Lie algebra,

$$
\operatorname{tr}_R T^a=0.
$$

So a possible mixed gravity–$G$ coefficient would be proportional to a sum of traces of non-Abelian generators, and it vanishes representation by representation:

$$
C_{Ggg}\propto\sum_{\psi_L}\operatorname{tr}_{R_\psi}(T^a)=0.
$$

This is different from the ordinary non-Abelian cubic gauge anomaly, which involves

$$
\operatorname{tr}_R\left(T^a\{T^b,T^c\}\right).
$$

A cubic trace can be nonzero for complex representations of $SU(N)$ with $N\ge3$. A single trace of a non-Abelian generator cannot.

For $U(1)$, the generator is just the charge $q$ times the identity on the internal multiplet, so the trace is not automatically zero:

$$
\operatorname{tr}_{\text{multiplet}}(q\mathbf1)=q\,d_{\rm multiplet}.
$$

That is why the mixed gravitational condition is a genuine constraint on Abelian gauge symmetries.

## Hypercharge in one generation

Using the all-left-handed Standard Model ledger,

$$
\begin{array}{c|c|c|c|c}
\text{field} & SU(3)_c & SU(2)_L & Y & \text{multiplicity} \\
\hline
Q_L & \mathbf3 & \mathbf2 & 1/6 & 6 \\
u_L^c & \overline{\mathbf3} & \mathbf1 & -2/3 & 3 \\
d_L^c & \overline{\mathbf3} & \mathbf1 & 1/3 & 3 \\
L_L & \mathbf1 & \mathbf2 & -1/2 & 2 \\
e_L^c & \mathbf1 & \mathbf1 & 1 & 1
\end{array}
$$

The mixed gravitational–hypercharge coefficient is

$$
C_{Ygg}=6\left(\frac{1}{6}\right)
+3\left(-\frac{2}{3}\right)
+3\left(\frac{1}{3}\right)
+2\left(-\frac{1}{2}\right)
+1.
$$

Term by term,

$$
C_{Ygg}=1-2+1-1+1=0.
$$

The cancellation has a nice interpretation. The colored quarks alone give

$$
1-2+1=0,
$$

while the leptons give

$$
-1+1=0.
$$

So in the usual hypercharge normalization the trace cancels separately in the quark and lepton sectors. This separate cancellation is not true for every anomaly equation: for example, the $[SU(2)_L]^2U(1)_Y$ anomaly cancels only after comparing the three colored quark doublets against the one lepton doublet.

Adding a sterile neutrino

$$
N_L^c\sim(\mathbf1,\mathbf1)_0
$$

changes nothing because its hypercharge is zero.

## Relation to the cubic hypercharge anomaly

The mixed gravitational condition is linear in $Y$:

$$
\operatorname{Tr}Y=0.
$$

The cubic hypercharge anomaly is cubic:

$$
\operatorname{Tr}Y^3=0.
$$

Both must vanish for a gauged $U(1)_Y$. They test different information.

For the observed one-generation Standard Model,

$$
\operatorname{Tr}Y^3
=6\left(\frac{1}{6}\right)^3
+3\left(-\frac{2}{3}\right)^3
+3\left(\frac{1}{3}\right)^3
+2\left(-\frac{1}{2}\right)^3
+1^3=0.
$$

The linear condition is less dramatic algebraically, but it is not redundant in a general chiral $U(1)$ theory. For arbitrary charges, $\sum q=0$ and $\sum q^3=0$ are independent. The Standard Model looks especially tidy because its charges also satisfy Yukawa relations and non-Abelian mixed anomaly constraints.

One way to see the logical role of $\operatorname{Tr}Y=0$ is the derivation in [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/). With Yukawa invariance and the $[SU(2)_L]^2U(1)_Y$ condition, the mixed gravitational equation gives

$$
Y_L+Y_H=0,
$$

which fixes the lepton doublet hypercharge relative to the Higgs.

## Mixed anomalies and gaugeability

A clean way to remember the rule is:

$$
\text{gauged current} \quad\Rightarrow\quad \text{all its gauge and mixed gravitational anomalies vanish}.
$$

For a global current, the situation is different. A global-current anomaly means the current is not exactly conserved in the quantum theory in the presence of background gauge or gravitational fields. This may be observable and useful. The axial anomaly is the classic example. The Standard Model baryon and lepton currents are another.

This distinction matters for possible extensions of the Standard Model. Suppose someone proposes to gauge a new $U(1)_X$. Then one must check all anomaly conditions involving $X$:

$$
[SU(3)_c]^2U(1)_X,
\qquad
[SU(2)_L]^2U(1)_X,
\qquad
[U(1)_Y]^2U(1)_X,
$$

$$
U(1)_Y[U(1)_X]^2,
\qquad
[U(1)_X]^3,
\qquad
[\text{gravity}]^2U(1)_X.
$$

The last one is the trace condition

$$
\operatorname{Tr}X=0.
$$

Failing it means the proposed $U(1)_X$ gauge symmetry is not consistent without adding new chiral matter or invoking additional anomaly-cancellation mechanisms.

## Example: gauging B minus L

The combination $B-L$ is special in the Standard Model. It has no electroweak instanton anomaly and is often considered for gauging. But the minimal Standard Model without right-handed neutrinos does not pass the mixed gravitational trace test for $B-L$.

In all-left-handed notation, the $B-L$ charges are

$$
\begin{array}{c|c|c}
\text{field} & B-L & \text{multiplicity} \\
\hline
Q_L & 1/3 & 6 \\
u_L^c & -1/3 & 3 \\
d_L^c & -1/3 & 3 \\
L_L & -1 & 2 \\
e_L^c & 1 & 1
\end{array}
$$

The trace is

$$
\operatorname{Tr}(B-L)
=6\left(\frac{1}{3}\right)
+3\left(-\frac{1}{3}\right)
+3\left(-\frac{1}{3}\right)
+2(-1)+1.
$$

Thus

$$
\operatorname{Tr}(B-L)=2-1-1-2+1=-1.
$$

This is not zero. If we add one sterile neutrino conjugate per generation,

$$
N_L^c\sim(\mathbf1,\mathbf1)_0,
\qquad
B-L=1,
$$

then

$$
\operatorname{Tr}(B-L)=-1+1=0.
$$

The same added field also helps cancel the cubic $[U(1)_{B-L}]^3$ anomaly. This is why gauged $B-L$ is naturally tied to right-handed neutrinos or equivalent new chiral matter. That link is not a proof that nature gauges $B-L$, but it is a very useful model-building diagnostic.

## Curved backgrounds are not optional bookkeeping

One might object: the Standard Model is usually studied in flat Minkowski spacetime, so why care about a gravitational background? The reason is conceptual. A local quantum field theory should make sense when coupled to nondynamical background fields for its currents and stress tensor, at least as a probe. If a gauge symmetry fails in such a background, it was not a robust gauge redundancy.

Equivalently, anomalies can be detected by the response of the fermion path-integral measure. A curved background lets the measure feel topology through curvature. The mixed gauge–gravitational anomaly is the statement that the gauge transformation of the fermion determinant can acquire a curvature-dependent phase unless $\operatorname{Tr}q=0$.

This viewpoint is also the doorway to modern anomaly inflow. A four-dimensional anomaly can often be represented by a higher-dimensional characteristic class. For this page we do not need the full machinery, but it is useful to remember that the triangle diagram is only one shadow of a more geometric object.

## Common mistakes

**Calling this a pure gravitational anomaly.** In four-dimensional Standard Model anomaly cancellation, the relevant condition is a mixed $U(1)$ gauge–gravitational anomaly. It tests the gauge current in a curved background. It is not a pure diffeomorphism anomaly.

**Forgetting spectator multiplicities.** The quark doublet contributes $6(1/6)$, not merely $1/6$. The color and weak multiplicities are part of the trace.

**Applying the trace condition to non-Abelian generators.** For semisimple non-Abelian groups, $\operatorname{tr}T^a=0$ representation by representation. The mixed gravitational trace condition is a real constraint for Abelian gauge factors.

**Assuming $\operatorname{Tr}Y=0$ follows from electric neutrality.** It does not. It is a sum over all left-handed Weyl components with multiplicity; it is not the total electric charge of a collection of particles.

**Gauging a global symmetry after checking only triangle anomalies with gauge bosons.** A proposed new $U(1)$ must also pass $[\text{gravity}]^2U(1)$. The $B-L$ example is the standard warning label.

## Exercises

### Exercise 1: Compute the Standard Model trace of hypercharge

Using the all-left-handed one-generation ledger, verify that $\operatorname{Tr}Y=0$.

<details><summary><strong>Solution</strong></summary>

The trace is

$$
\operatorname{Tr}Y
=6\left(\frac{1}{6}\right)
+3\left(-\frac{2}{3}\right)
+3\left(\frac{1}{3}\right)
+2\left(-\frac{1}{2}\right)
+1.
$$

Compute each contribution:

$$
1-2+1-1+1=0.
$$

Therefore the mixed gravitational–hypercharge anomaly cancels in one generation.

</details>

### Exercise 2: Show that vectorlike pairs do not contribute

A left-handed Weyl fermion has $U(1)$ charge $q$ and multiplicity $d$. Add another left-handed Weyl fermion in the conjugate representation with charge $-q$ and the same multiplicity. Show that their mixed gravitational anomaly cancels.

<details><summary><strong>Solution</strong></summary>

The contribution is

$$
dq+d(-q)=0.
$$

This is the mixed gravitational version of the general statement that vectorlike pairs do not produce gauge anomalies.

</details>

### Exercise 3: Test minimal B minus L

Using the all-left-handed charges

$$
Q_L:\frac{1}{3},
\qquad
u_L^c:-\frac{1}{3},
\qquad
d_L^c:-\frac{1}{3},
\qquad
L_L:-1,
\qquad
e_L^c:1,
$$

show that the minimal Standard Model without $N_L^c$ has $\operatorname{Tr}(B-L)=-1$ per generation.

<details><summary><strong>Solution</strong></summary>

Include multiplicities:

$$
\operatorname{Tr}(B-L)
=6\left(\frac{1}{3}\right)+3\left(-\frac{1}{3}\right)+3\left(-\frac{1}{3}\right)+2(-1)+1.
$$

Thus

$$
\operatorname{Tr}(B-L)=2-1-1-2+1=-1.
$$

So $B-L$ cannot be gauged in the minimal field content without additional anomaly-cancelling matter.

</details>

### Exercise 4: Add a right-handed neutrino conjugate

Add $N_L^c$ with $B-L=1$. Show that $\operatorname{Tr}(B-L)$ vanishes.

<details><summary><strong>Solution</strong></summary>

The sterile conjugate has multiplicity $1$ and $B-L=1$, so it contributes $+1$ to the trace. The minimal trace was $-1$, hence

$$
-1+1=0.
$$

This cancels the mixed gravitational anomaly for gauged $B-L$ per generation.

</details>

## Relations to other pages

- [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/) uses the mixed gravitational equation as one ingredient in deriving the Standard Model hypercharge pattern.
- [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) includes the explicit $\operatorname{Tr}Y=0$ check alongside the gauge-triangle checks.
- [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/) separates gauge consistency from anomalous global-current physics.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explains the minimal lepton-number-violating operator, which is closely related to why $B-L$ and neutrino masses are often discussed together.
- [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) explains why neutrino mass motivates extensions of the minimal fermion content.

## Research status

The mixed gravitational–hypercharge cancellation is established textbook physics. The active frontier is the broader anomaly framework: anomaly inflow, global anomalies, cobordism constraints, generalized symmetries, and the anomaly structure of possible Standard Model extensions.

## Where to go next

Continue to [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/). The mixed gravitational anomaly is still a local perturbative condition. The global $SU(2)$ anomaly is different: it is a nonperturbative sign obstruction that sees topology not captured by triangle diagrams.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomalies, and Standard Model sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the anomaly chapter.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory and its anomaly-cancellation discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and anomaly constraints.
- Reviews on anomaly inflow and gravitational contributions to current anomalies for the characteristic-class viewpoint.

## Version history

- **2026-06-19:** Initial page explaining the mixed gravitational–hypercharge anomaly and the $\operatorname{Tr}Y=0$ Standard Model cancellation.
