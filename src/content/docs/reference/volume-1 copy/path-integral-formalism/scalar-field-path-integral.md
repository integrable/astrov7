---
title: "Scalar Field Path Integral"
description: "The Lorentzian functional integral for a real scalar field, its Gaussian free-field evaluation, source differentiation, propagator inversion, interactions, Euclidean continuation, and measure caveats."
sidebar:
  label: "Scalar Field Path Integral"
  order: 3
---

## Summary

The scalar-field path integral is the field-theory analogue of the quantum-mechanical path integral. Instead of integrating over paths $q(t)$, we integrate over field configurations $\phi(x)$:

$$
\boxed{
Z[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{iS[\phi]+i\int d^4x\,J(x)\phi(x)\right\},
\qquad Z[0]=1.
}
$$

For the free real scalar field, using qft.org's mostly-minus metric convention,

$$
S_0[\phi]
=\int d^4x\left[\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2\right],
$$

and the normalized source functional is

$$
\boxed{
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
}
$$

where

$$
\boxed{
D_F(x-y)=\int\frac{d^4p}{(2\pi)^4}
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

Correlation functions come from functional differentiation:

$$
\boxed{
\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle
=\left.\frac{1}{i^n}
\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
}
$$

This page is the bridge from the quantum-mechanical path integral to field-theory generating functionals. Coleman presents $Z[J]$ as the vacuum-to-vacuum functional in an external source and emphasizes that the functional integral replaces operator commutators by ordinary integrations over c-number fields, while Weinberg derives the same Lorentz-covariant Feynman rules by starting from the canonical formalism (Coleman 2019, ch. 28; Weinberg 1995, Vol. I, §§9.1–9.4).

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), and [Quantum-Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/).

## Core idea

A scalar field has one degree of freedom at each spatial point. In the path integral, a field history assigns a value to each spacetime point. A regulated version turns spacetime into a lattice, integrates over one variable per site, and then takes a continuum limit.

<figure class="doc-figure" style="--figure-width: 50rem;">

![From many field variables to the scalar-field path integral](/figures/foundations/scalar-field-functional-integral.svg)

<figcaption>

A scalar-field path integral is the continuum limit of many ordinary integrals, one for each regulated field variable. The free Gaussian produces three standard outputs: a determinant, the Feynman propagator $D_F$, and Wick pairings. Interactions are added by expanding non-quadratic terms around this Gaussian.

</figcaption>
</figure>

The analogy with ordinary quantum mechanics is direct:

| Ordinary quantum mechanics | Scalar field theory |
|---|---|
| coordinate $q(t)$ | field $\phi(t,\mathbf x)$ |
| path $q(t)$ | field history $\phi(x)$ |
| action $S[q]$ | action $S[\phi]$ |
| source $j(t)q(t)$ | source $J(x)\phi(x)$ |
| oscillator Green function | Feynman propagator |

The field integral is infinite-dimensional, so the table is a guide to the construction, not a rigorous measure-theory theorem.

## From many coordinates to a field

Imagine regulating space by putting the scalar field in a box and discretizing space into $N$ points. The field becomes a large list of coordinates,

$$
\phi_i(t),
\qquad i=1,\ldots,N.
$$

The classical action becomes a many-coordinate action of the form

$$
S[\phi_i]
=\int dt\left[\frac12\sum_i a^3 \dot\phi_i^2
-\frac12\sum_{i,j}\phi_i K_{ij}\phi_j
+\cdots\right],
$$

where $a$ is the lattice spacing, $K_{ij}$ contains the mass term and the finite-difference approximation to spatial gradients, and the dots denote interactions.

The quantum-mechanical path integral for many coordinates is

$$
\int\prod_i\mathcal D\phi_i(t)\,e^{iS[\phi_i]}.
$$

The formal continuum notation

$$
\int\mathcal D\phi\,e^{iS[\phi]}
$$

is a compressed way to say

```txt
regulate the field theory,
integrate over finitely many variables,
then study the continuum limit.
```

This is why the field path integral should not be read as a single, already-defined infinite product. The definition depends on regularization, boundary conditions, and the class of observables under discussion.

## Lorentzian scalar functional integral

For the real scalar field,

$$
\mathcal L_0
=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2.
$$

With a source,

$$
\mathcal L_J
=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2+J\phi.
$$

The normalized Lorentzian generating functional is

$$
Z[J]
=\frac{\int\mathcal D\phi\,e^{iS[\phi]+i\int J\phi}}
{\int\mathcal D\phi\,e^{iS[\phi]}}.
$$

Equivalently, write

$$
Z[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,e^{iS[\phi]+i\int J\phi},
\qquad
\mathcal N=\int\mathcal D\phi\,e^{iS[\phi]}.
$$

The source $J(x)$ is not a physical field in this context. It is a bookkeeper. Differentiating with respect to $J$ inserts fields into a time-ordered vacuum correlator.

:::note[Assumptions]
This page treats a real scalar field in the ordinary Minkowski vacuum. Gauge fields, constrained systems, fermions, curved backgrounds, finite temperature, and nontrivial topological sectors require additional structure: gauge fixing, ghosts, Grassmann variables, boundary conditions, or sums over sectors.
:::

## Free theory as a Gaussian

Integrate the free action by parts and ignore boundary terms:

$$
S_0[\phi]
=\frac12\int d^4x\,\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\int d^4x\,\phi^2
=-\frac12\int d^4x\,\phi(\Box+m^2)\phi.
$$

The Lorentzian integral is oscillatory, so the inverse operator must be specified by a prescription. Insert the Feynman prescription by writing

$$
S_{0,\epsilon}[\phi]
=-\frac12\int d^4x\,\phi(\Box+m^2-i\epsilon)\phi.
$$

Then

$$
Z_0[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{i\left[-\frac12\int\phi(\Box+m^2-i\epsilon)\phi
+\int J\phi\right]\right\}.
$$

This is the infinite-dimensional version of the Gaussian identity

$$
\int d^Nx\,\exp\left[-\frac{i}{2}x^TKx+iJ^Tx\right]
\propto
\exp\left[\frac{i}{2}J^TK^{-1}J\right].
$$

Here

$$
K=\Box+m^2-i\epsilon.
$$

The inverse is related to the Feynman propagator by

$$
K^{-1}=iD_F,
$$

because

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

Therefore

$$
\boxed{
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right].
}
$$

This is the exact free scalar answer. It is the same object obtained by canonical quantization from the time-ordered two-point function. Weinberg derives the scalar propagator as the inverse of the quadratic kernel in the path integral, while Coleman obtains the free source functional by reducing the functional integral to a Gaussian (Weinberg 1995, Vol. I, §9.4; Coleman 2019, §§28.2–28.3).

## Correlators from source derivatives

The source functional is normalized so that

$$
Z_0[0]=1.
$$

The one-point function is

$$
\langle0|T\phi(x)|0\rangle
=\left.\frac{1}{i}\frac{\delta Z_0[J]}{\delta J(x)}\right|_{J=0}=0.
$$

The two-point function is

$$
\begin{aligned}
\langle0|T\{\phi(x)\phi(y)\}|0\rangle
&=\left.\frac{1}{i^2}\frac{\delta^2Z_0[J]}{\delta J(x)\delta J(y)}\right|_{J=0} \\
&=D_F(x-y).
\end{aligned}
$$

Higher free correlators are sums over pairings. For example,

$$
\begin{aligned}
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
=&\,D_F(1,2)D_F(3,4)\\
&+D_F(1,3)D_F(2,4)\\
&+D_F(1,4)D_F(2,3),
\end{aligned}
$$

where $\phi_i=\phi(x_i)$ and $D_F(i,j)=D_F(x_i-x_j)$. This is Wick's theorem in source-functional form.

The free connected generating functional is especially simple. Since

$$
Z_0[J]=e^{iW_0[J]},
$$

we have

$$
W_0[J]=\frac{i}{2}\int d^4x\,d^4y\,J(x)D_F(x-y)J(y).
$$

It is quadratic in $J$. Therefore all connected free correlators beyond the two-point function vanish.

## Momentum-space form

Translation invariance gives

$$
D_F(x-y)=\int\frac{d^4p}{(2\pi)^4}\,e^{-ip\cdot(x-y)}D_F(p),
$$

with

$$
\boxed{
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
}
$$

In momentum space,

$$
Z_0[J]
=\exp\left[-\frac12\int\frac{d^4p}{(2\pi)^4}\,
J(p)D_F(p)J(-p)\right],
$$

assuming the Fourier convention fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

The $i\epsilon$ term does two jobs at once:

```txt
1. It specifies the inverse of the Klein–Gordon operator.
2. It selects the vacuum time-ordering boundary condition.
```

This is why the path-integral Gaussian and the operator Feynman propagator agree.

## Adding interactions

For an interacting scalar theory, write

$$
S[\phi]=S_0[\phi]+S_{\mathrm{int}}[\phi].
$$

For example,

$$
S_{\mathrm{int}}[\phi]
=\int d^4x\left[-\frac{\lambda}{4!}\phi^4(x)\right]
$$

for $\phi^4$ theory.

The source functional becomes

$$
Z[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{iS_0[\phi]+iS_{\mathrm{int}}[\phi]+i\int J\phi\right\}.
$$

Perturbation theory expands $e^{iS_{\mathrm{int}}}$ around the free Gaussian. The useful formal identity is

$$
Z[J]
=\frac{1}{\mathcal N}
\exp\left[iS_{\mathrm{int}}\left(\frac{1}{i}\frac{\delta}{\delta J}\right)\right]Z_0[J].
$$

For $\phi^4$ theory,

$$
\exp\left[iS_{\mathrm{int}}\left(\frac{1}{i}\frac{\delta}{\delta J}\right)\right]
=
\exp\left[-i\frac{\lambda}{4!}\int d^4x\,
\left(\frac{1}{i}\frac{\delta}{\delta J(x)}\right)^4\right].
$$

The functional derivatives act on the free Gaussian and generate contractions. Diagrammatically, the Gaussian supplies propagator lines and $S_{\mathrm{int}}$ supplies vertices. This is the functional-integral route to Feynman diagrams.

The next pages develop this source technology more systematically; the present page's goal is only to show how the free scalar Gaussian and its perturbative deformation are set up.

## Vacuum bubbles and normalization

The denominator in

$$
Z[J]=\frac{\int\mathcal D\phi\,e^{iS+i\int J\phi}}
{\int\mathcal D\phi\,e^{iS}}
$$

removes source-independent vacuum-to-vacuum factors. Diagrammatically, it cancels disconnected vacuum bubbles that do not attach to source insertions. This is why $Z[0]=1$.

For connected correlators, one defines

$$
Z[J]=e^{iW[J]}.
$$

The logarithm removes disconnected pieces and leaves connected diagrams. This is the functional-integral version of the cumulant discussion in [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/).

## Euclidean scalar field

The Lorentzian scalar path integral

$$
\int\mathcal D\phi\,e^{iS[\phi]}
$$

is oscillatory. Under the Wick rotation

$$
t=-i\tau,
$$

the free scalar action becomes

$$
S_E[\phi]
=\int d^4x_E\left[\frac12(\partial_\mu^E\phi)^2+\frac12m^2\phi^2\right],
$$

and the weight becomes

$$
e^{-S_E[\phi]}.
$$

With a Euclidean source,

$$
Z_E[J]
=\frac{1}{\mathcal N_E}
\int\mathcal D\phi\,
\exp\left[-S_E[\phi]+\int d^4x_E\,J\phi\right].
$$

For the free theory,

$$
Z_{E,0}[J]
=\exp\left[\frac12\int d^4x_Ed^4y_E\,J(x)G_E(x-y)J(y)\right],
$$

where

$$
(-\partial_E^2+m^2)G_E(x-y)=\delta^{(4)}(x-y).
$$

The Euclidean theory is often the cleanest way to define and regulate scalar QFT, but it is not automatically equivalent to a unitary Lorentzian theory. Reflection positivity and analytic continuation are the bridge.

## Measure caveats

For a free scalar field in Cartesian variables, the formal measure is usually written

$$
\mathcal D\phi=\prod_x d\phi(x).
$$

This notation hides several important facts.

First, the product over $x$ is meaningless until regulated. A lattice regulator replaces it by

$$
\prod_i d\phi_i.
$$

Second, field redefinitions can produce Jacobians. In simple perturbative scalar theories such Jacobians are often harmless or absorbed into counterterms, but in more general theories they matter.

Third, zero modes make Gaussian determinants singular. If the quadratic operator has a zero eigenvalue, the inverse propagator does not exist until the zero mode is treated separately. Gauge theories have infinitely many such redundant directions before gauge fixing.

Fourth, Lorentzian convergence is not guaranteed by the symbol $i\epsilon$. The prescription tells us how to define distributions and vacuum boundary conditions; fully nonperturbative real-time path integrals are delicate.

## Operator and path-integral dictionary

| Operator language | Path-integral language |
|---|---|
| vacuum expectation value | normalized functional integral |
| time ordering | source functional derivatives |
| Feynman propagator | inverse quadratic kernel with Feynman prescription |
| Wick contractions | Gaussian pairings |
| vacuum bubble cancellation | normalization by $Z[0]$ |
| connected correlators | logarithm $W=-i\log Z$ |
| interaction Hamiltonian expansion | expansion of $e^{iS_{\mathrm{int}}}$ |
| canonical unitarity | not manifest; inherited when derived from canonical theory |

Neither language replaces the other. Operator methods keep the Hilbert-space interpretation close; path integrals make covariance, sources, saddle points, and perturbative bookkeeping spectacularly efficient.

## Common pitfalls

### Thinking field configurations are particle trajectories

A field configuration $\phi(x)$ assigns a number to every spacetime point. It is not the worldline of a particle. Particle language reappears in poles, external states, and asymptotic Hilbert-space interpretations.

### Dropping the normalization

Without the normalization by $\mathcal N$ or $Z[0]$, source-independent vacuum bubbles remain. They usually cancel in normalized correlators, but they matter for vacuum energy, effective actions, and gravity.

### Forgetting the prescription

The inverse of $\Box+m^2$ is not unique. Feynman, retarded, advanced, and other Green functions are different inverses with different boundary conditions. The vacuum path integral gives the Feynman inverse.

### Treating the measure as invariant by wishful thinking

Some transformations change the measure by a Jacobian. This is the path-integral origin of many anomaly calculations. The scalar examples here are deliberately tame.

### Equating Euclidean convergence with Lorentzian unitarity

A well-behaved Euclidean integral is valuable, but a Lorentzian unitary QFT requires more. Reflection positivity is the key structural condition.

## Relation to other topics

- [Quantum-Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/) gives the time-sliced origin of the formalism.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) develops $Z[J]$, $W[J]$, classical fields, and functional derivatives in detail.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) explains Wick rotation and Euclidean correlators.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) turns the Gaussian pairing rule into perturbation theory.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) interprets the expansion of $e^{iS_{\mathrm{int}}}$ diagrammatically.
- [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) treats Jacobians, zero modes, and anomaly previews.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) explains why gauge-field path integrals need extra structure.

## Research status

- **Established:** The perturbative scalar-field path integral and its equivalence to canonical free-field correlators are standard textbook QFT.
- **Subtle:** The continuum measure, Lorentzian convergence, field redefinitions, zero modes, and nonperturbative definitions require regulators and care.
- **Bridge:** This page prepares for generating functionals, Euclidean QFT, Grassmann integrals, and perturbative Feynman rules.

## Exercises

### Exercise 1: Free scalar kernel

Show that

$$
S_0[\phi]
=\int d^4x\left[\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2\right]
$$

can be written, up to a boundary term, as

$$
S_0[\phi]
=-\frac12\int d^4x\,\phi(\Box+m^2)\phi.
$$

<details>
<summary><strong>Solution</strong></summary>

Use integration by parts:

$$
\int d^4x\,\partial_\mu\phi\partial^\mu\phi
=-\int d^4x\,\phi\partial_\mu\partial^\mu\phi
+\text{boundary}.
$$

Since

$$
\Box=\partial_\mu\partial^\mu,
$$

we get

$$
S_0[\phi]
=-\frac12\int d^4x\,\phi\Box\phi
-\frac12m^2\int d^4x\,\phi^2
+\text{boundary}.
$$

Therefore

$$
S_0[\phi]
=-\frac12\int d^4x\,\phi(\Box+m^2)\phi
+\text{boundary}.
$$

</details>

### Exercise 2: Source derivative gives the two-point function

Starting from

$$
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
$$

show that

$$
\left.\frac{1}{i^2}\frac{\delta^2Z_0[J]}{\delta J(x)\delta J(y)}\right|_{J=0}
=D_F(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

First differentiate:

$$
\frac{\delta Z_0}{\delta J(x)}
=-\left(\int d^4z\,D_F(x-z)J(z)\right)Z_0[J].
$$

Differentiating again gives

$$
\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}
=-D_F(x-y)Z_0[J]
+\left(\int d^4z\,D_F(x-z)J(z)\right)
\left(\int d^4w\,D_F(y-w)J(w)\right)Z_0[J].
$$

At $J=0$, the second term vanishes and $Z_0[0]=1$, so

$$
\left.\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}\right|_{J=0}
=-D_F(x-y).
$$

Since $1/i^2=-1$,

$$
\left.\frac{1}{i^2}\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}\right|_{J=0}
=D_F(x-y).
$$

</details>

### Exercise 3: Free connected four-point function

Use

$$
Z_0[J]=e^{iW_0[J]},
\qquad
W_0[J]=\frac{i}{2}\int J D_F J,
$$

to show that the connected four-point function of a free scalar field vanishes.

<details>
<summary><strong>Solution</strong></summary>

Connected correlators are generated by functional derivatives of $W[J]$. The free $W_0[J]$ is quadratic in $J$:

$$
W_0[J]=\frac{i}{2}\int d^4x\,d^4y\,J(x)D_F(x-y)J(y).
$$

Any fourth functional derivative of a quadratic functional is zero:

$$
\frac{\delta^4W_0[J]}{\delta J(x_1)\delta J(x_2)\delta J(x_3)\delta J(x_4)}=0.
$$

Therefore

$$
G_4^{\mathrm c}(x_1,x_2,x_3,x_4)=0
$$

for the free scalar field.

</details>

### Exercise 4: Propagator equation

Using

$$
D_F(x)=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i e^{-ip\cdot x}}{p^2-m^2+i\epsilon},
$$

show that

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x)
$$

up to the usual infinitesimal prescription.

<details>
<summary><strong>Solution</strong></summary>

Acting on the plane wave gives

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}.
$$

Therefore

$$
(\Box+m^2)D_F(x)
=\int\frac{d^4p}{(2\pi)^4}\,
(-p^2+m^2)\frac{i e^{-ip\cdot x}}{p^2-m^2+i\epsilon}.
$$

For nonzero infinitesimal $\epsilon$,

$$
(-p^2+m^2)\frac{i}{p^2-m^2+i\epsilon}
=-i\frac{p^2-m^2}{p^2-m^2+i\epsilon}.
$$

As a distribution, the ratio tends to $1$ away from the prescribed pole singularity. Thus

$$
(\Box+m^2)D_F(x)
=-i\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}
=-i\delta^{(4)}(x).
$$

</details>

### Exercise 5: Euclidean scalar Gaussian

For the Euclidean action

$$
S_E[\phi]=\frac12\int d^4x_E\,\phi(-\partial_E^2+m^2)\phi,
$$

show that

$$
Z_{E,0}[J]
=\exp\left[\frac12\int JG_EJ\right],
$$

where

$$
(-\partial_E^2+m^2)G_E(x-y)=\delta^{(4)}(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

This is the finite-dimensional Euclidean Gaussian with

$$
A=-\partial_E^2+m^2.
$$

Completing the square gives

$$
-\frac12\phi A\phi+J\phi
=-\frac12(\phi-A^{-1}J)A(\phi-A^{-1}J)
+\frac12JA^{-1}J.
$$

The shifted Gaussian contributes a $J$-independent factor that cancels in the normalized functional. Since $A^{-1}=G_E$,

$$
Z_{E,0}[J]
=\exp\left[\frac12\int d^4x_Ed^4y_E\,J(x)G_E(x-y)J(y)\right].
$$

</details>

### Exercise 6: First interaction correction

For $\phi^4$ theory with

$$
S_{\mathrm{int}}=-\frac{\lambda}{4!}\int d^4x\,\phi^4(x),
$$

write the first-order correction to $Z[J]$ in terms of functional derivatives acting on $Z_0[J]$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\phi(x)\longrightarrow \frac{1}{i}\frac{\delta}{\delta J(x)}.
$$

To first order in $\lambda$,

$$
e^{iS_{\mathrm{int}}}
=1+iS_{\mathrm{int}}+O(\lambda^2).
$$

Therefore

$$
Z[J]
=\frac{1}{\mathcal N}
\left[1-i\frac{\lambda}{4!}\int d^4x\,
\left(\frac{1}{i}\frac{\delta}{\delta J(x)}\right)^4
+O(\lambda^2)\right]Z_0[J].
$$

The normalization $\mathcal N$ is chosen so that $Z[0]=1$, which removes the source-independent vacuum bubble contribution.

</details>

## Sources and further reading

### Primary references

- P. A. M. Dirac, “The Lagrangian in Quantum Mechanics,” *Physikalische Zeitschrift der Sowjetunion* **3** (1933), for the action-based short-time viewpoint.
- R. P. Feynman, “Space-Time Approach to Non-Relativistic Quantum Mechanics,” *Reviews of Modern Physics* **20** (1948), for the path-integral formulation.
- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), for the gauge-theory path-integral development beyond scalar fields.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§8–9, for the free and interacting scalar path integrals.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 28, for functional integration, Euclidean continuation, and Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§9.1–9.4, for the derivation of path integrals from canonical quantum mechanics and the path-integral derivation of propagators.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.2–I.3 and appendix A, for the intuitive path-integral viewpoint and Gaussian identity.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9.1–9.2, for generating functionals and scalar field path integrals.

### For a first pass

- Srednicki, §§8–9.
- Zee, chs. I.2–I.3 and appendix A.
- Peskin and Schroeder, §9.1.

### For mathematical precision

- B. Simon, *Functional Integration and Quantum Physics*, for rigorous aspects of functional integration.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for Euclidean constructive field theory.
- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” for the reconstruction conditions connecting Euclidean correlators to Lorentzian QFT.

## Version history

- **2026-05-23:** Initial qft.org page on the Lorentzian scalar-field path integral, the free Gaussian source functional, functional differentiation, interaction expansion, Euclidean continuation, normalization, and measure caveats.
