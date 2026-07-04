---
title: "Ward Identities and Anomalies"
description: "How gauge invariance, diffeomorphism invariance, and Weyl transformations become holographic Ward identities, and how logarithmic counterterms encode anomalies."
sidebar:
  order: 50
---

The previous pages made the on-shell action finite and showed how to vary it. We now extract one of the main rewards of holographic renormalization: the Ward identities of the boundary theory.

A Ward identity is the equation that follows when a generating functional is invariant under a symmetry. In holography the same equation has a second life: it is a radial constraint equation of the bulk theory. Gauge invariance gives current conservation. Boundary diffeomorphism invariance gives stress-tensor conservation, possibly modified by external sources. Weyl transformations give the trace Ward identity, including conformal anomalies.

The useful slogan is

$$
\text{bulk radial constraints}
\quad\longleftrightarrow\quad
\text{boundary Ward identities}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic map from the renormalized generating functional to the gauge, diffeomorphism, and Weyl Ward identities. The gauge identity comes from the bulk Gauss constraint, the diffeomorphism identity from the momentum constraint, and the trace identity from the Hamiltonian constraint. Logarithmic counterterms produce the anomaly.](/figures/course/holographic-ward-identities-anomalies.svg)

<figcaption>

The three basic holographic Ward identities. Gauge transformations, boundary diffeomorphisms, and Weyl transformations act on the sources in $W_{\rm ren}$. In the bulk, the same statements are the Gauss, momentum, and Hamiltonian constraints. Logarithmic counterterms produce the local anomaly density $\mathcal A$.

</figcaption>
</figure>

## Why this matters

Ward identities are not optional consistency checks. They are part of the dictionary.

If a holographic computation gives a stress tensor that is not conserved in a background where it should be conserved, something is wrong: perhaps the counterterms are incomplete, the boundary variation was not performed at fixed source, the gauge choice hid a constraint, or the sign convention for the outward normal was changed halfway through the calculation.

Ward identities also explain why holographic renormalization is local. The divergent terms in the on-shell action are constrained by covariance, gauge invariance, and Weyl scaling. The same local terms that cancel divergences also know about trace anomalies and scheme dependence.

The most important practical lesson is this:

$$
\boxed{\text{the finite one-point functions must obey the renormalized Ward identities.}}
$$

This is why one-point functions are best defined by varying $S_{\rm ren}$, not by reading off a single coefficient from a near-boundary expansion without checking counterterms.

## Setup: sources and one-point functions

Let the boundary generating functional depend on a metric source $g_{(0)ij}$, background gauge fields $A_{(0)i}^a$, and scalar sources $\lambda^I$ coupled to scalar operators $\mathcal O_I$:

$$
W_{\rm CFT}[g_{(0)},A_{(0)},\lambda]
=
\log Z_{\rm CFT}[g_{(0)},A_{(0)},\lambda].
$$

The variation convention on this page is

$$
\delta W_{\rm CFT}
=
\int d^d x\sqrt{g_{(0)}}
\left(
\frac12 \langle T^{ij}\rangle\delta g_{(0)ij}
+
\langle J_a^i\rangle\delta A_{(0)i}^a
+
\langle \mathcal O_I\rangle\delta\lambda^I
\right).
$$

In the classical Euclidean gravity approximation,

$$
W_{\rm CFT}
\approx
-S_{\text{ren,on-shell}}.
$$

Thus, if one differentiates $S_{\rm ren}$ directly instead of $W_{\rm CFT}$, one must insert the corresponding minus sign. Most apparent sign disagreements in the holographic Ward identities trace back to this choice.

For compactness, we now suppress the subscript $(0)$ on boundary sources and write

$$
g_{ij}\equiv g_{(0)ij},
\qquad
A_i^a\equiv A_{(0)i}^a.
$$

## Gauge Ward identity

Start with a background gauge transformation with parameter $\alpha^a(x)$. The gauge field transforms as

$$
\delta_\alpha A_i^a = D_i\alpha^a,
$$

where $D_i$ is the background gauge-covariant derivative. If the scalar sources $\lambda^I$ transform in a representation of the symmetry group,

$$
\delta_\alpha \lambda^I
=
-\alpha^a(T_a\lambda)^I.
$$

Gauge invariance of the generating functional gives $\delta_\alpha W=0$. Using the variational formula,

$$
0
=
\int d^d x\sqrt g
\left(
\langle J_a^i\rangle D_i\alpha^a
-
\langle \mathcal O_I\rangle\alpha^a(T_a\lambda)^I
\right).
$$

After integrating by parts, and using that $\alpha^a(x)$ is arbitrary, we obtain

$$
\boxed{
D_i\langle J_a^i\rangle
=
-\langle \mathcal O_I\rangle (T_a\lambda)^I.
}
$$

For neutral scalar sources, or when the charged sources are set to zero, this reduces to

$$
D_i\langle J_a^i\rangle=0.
$$

### Bulk interpretation

The bulk version is the radial Gauss constraint. Consider a bulk gauge field $A_M^a$ with radial canonical momentum

$$
\Pi_a^i
=
\frac{\delta S_{\rm reg}}{\delta A_i^a}.
$$

The radial component of the gauge-field equation is not a dynamical evolution equation. It is a constraint. Schematically,

$$
D_i\Pi_a^i + \text{charged matter contribution}=0.
$$

After adding counterterm contributions and taking the cutoff away, $\Pi_a^i$ becomes the renormalized current $\langle J_a^i\rangle$. The Gauss constraint becomes the gauge Ward identity.

This is the cleanest example of the general idea: a bulk gauge redundancy becomes a boundary conservation law.

## Diffeomorphism Ward identity

Now consider an infinitesimal boundary diffeomorphism generated by a vector field $\xi^i(x)$. The sources transform by Lie derivatives:

$$
\delta_\xi g_{ij}=\nabla_i\xi_j+\nabla_j\xi_i,
$$

$$
\delta_\xi \lambda^I=\xi^j\partial_j\lambda^I,
$$

and

$$
\delta_\xi A_i^a
=
\xi^jF_{ji}^a+D_i(\xi^jA_j^a).
$$

The last expression writes the Lie derivative of a gauge field as a gauge-covariant piece plus a gauge transformation. Using the gauge Ward identity to remove the pure gauge part, diffeomorphism invariance gives

$$
\boxed{
\nabla_i\langle T^i{}_{j}\rangle
=
F_{ji}^a\langle J_a^i\rangle
+
\langle \mathcal O_I\rangle\partial_j\lambda^I.
}
$$

This equation is not saying that energy-momentum is mysteriously nonconserved. It says that the CFT is exchanging energy and momentum with external background sources.

If the scalar sources are constant and no background gauge field strength is turned on, then

$$
\nabla_i\langle T^i{}_{j}\rangle=0.
$$

If the theory is placed in an external electromagnetic field, the term

$$
F_{ji}\langle J^i\rangle
$$

is the Lorentz-force density exerted by the background field on the charged degrees of freedom. If a coupling $\lambda(x)$ varies in spacetime, the term

$$
\langle\mathcal O\rangle\partial_j\lambda
$$

is the force density due to the explicit spacetime dependence of the coupling.

### Bulk interpretation

The bulk version is the momentum constraint. In radial Hamiltonian language, it is generated by diffeomorphisms tangent to the cutoff surface $\Sigma_\epsilon$.

For pure gravity plus matter, the momentum constraint has the schematic form

$$
-2D_j\pi^j{}_i
+
\Pi_\phi\partial_i\phi
+
F_{ij}^a\Pi_a^j
+
\cdots
=0.
$$

Here $\pi^{ij}$ is the canonical momentum conjugate to the induced metric $\gamma_{ij}$, $\Pi_\phi$ is the momentum conjugate to the scalar, and $\Pi_a^i$ is the momentum conjugate to the gauge field. After renormalization,

$$
\pi^{ij}_{\rm ren}
\longrightarrow
\frac12\sqrt g\,\langle T^{ij}\rangle,
\qquad
\Pi_{a,\rm ren}^i
\longrightarrow
\sqrt g\,\langle J_a^i\rangle,
\qquad
\Pi_{I,\rm ren}
\longrightarrow
\sqrt g\,\langle\mathcal O_I\rangle.
$$

The momentum constraint becomes the diffeomorphism Ward identity.

## Weyl Ward identity

A conformal field theory has a special response to Weyl transformations of the background metric. Let

$$
\delta_\sigma g_{ij}=2\sigma(x)g_{ij}.
$$

A scalar source $\lambda^I$ for an operator of dimension $\Delta_I$ has Weyl weight $\Delta_I-d$:

$$
\delta_\sigma\lambda^I=(\Delta_I-d)\sigma\lambda^I
$$

near a conformal fixed point. If the renormalized generating functional were exactly Weyl invariant, the variation would vanish. Quantum mechanically, in even boundary dimension, it may instead produce a local anomaly:

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\,\mathcal A.
$$

Using the variational formula, we get

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma
\left(
\langle T^i{}_{i}\rangle
+
\sum_I(\Delta_I-d)\lambda^I\langle\mathcal O_I\rangle
\right).
$$

Therefore

$$
\boxed{
\langle T^i{}_{i}\rangle
=
\sum_I(d-\Delta_I)\lambda^I\langle\mathcal O_I\rangle
+
\mathcal A.
}
$$

This is the trace Ward identity.

If all scalar sources vanish and there is no Weyl anomaly, then

$$
\langle T^i{}_{i}\rangle=0.
$$

If a relevant deformation is turned on, $\Delta<d$, then the source explicitly introduces a scale and the trace is nonzero even in flat space:

$$
\langle T^i{}_{i}\rangle
=
(d-\Delta)\lambda\langle\mathcal O\rangle
+
\mathcal A.
$$

For a marginal coupling, the classical source term vanishes. Away from an exact fixed point, the local RG form replaces $(\Delta_I-d)\lambda^I$ by the beta function $\beta^I(\lambda)$:

$$
\langle T^i{}_{i}\rangle
=
\beta^I(\lambda)\langle\mathcal O_I\rangle
+
\mathcal A.
$$

In the canonical $\mathcal N=4$ SYM example, the gauge coupling is exactly marginal, so this beta-function term vanishes.

## Where the anomaly comes from

The Weyl anomaly is the finite memory of a logarithmic divergence. Suppose the regulated on-shell action contains a term of the form

$$
S_{\log}
=
\log(\epsilon\mu)
\int d^d x\sqrt{g}\,\mathcal A[g,A,\lambda].
$$

Here $\epsilon$ is the radial cutoff and $\mu$ is the renormalization scale introduced to make the logarithm dimensionless. The counterterm cancels the divergence as $\epsilon\to0$, but the scale $\mu$ remains. Equivalently, changing $\mu$ changes the finite renormalized action by a local functional.

This local functional is the anomaly.

A quick way to remember the logic is

$$
\boxed{
\text{logarithmic radial divergence}
\quad\longleftrightarrow\quad
\text{boundary Weyl anomaly}.
}
$$

Power-law divergences can be subtracted without leaving an invariant finite trace. Logarithmic divergences are different because $\log(\epsilon\mu)$ changes by an additive constant under rescaling. That additive constant is physical up to the usual scheme-dependent local terms.

## Examples of trace anomalies

In a two-dimensional CFT on a curved Euclidean background, the trace anomaly takes the form

$$
\langle T^i{}_{i}\rangle
=
\frac{c}{24\pi}R
$$

up to sign conventions for the Euclidean effective action and curvature. In holographic AdS$_3$/CFT$_2$, the Brown–Henneaux central charge is

$$
c=\frac{3L}{2G_3}.
$$

In a four-dimensional CFT, the purely gravitational trace anomaly is usually written as

$$
\langle T^i{}_{i}\rangle
=
\frac{c}{16\pi^2}W_{ijkl}W^{ijkl}
-
\frac{a}{16\pi^2}E_4
+
\kappa\Box R
+
\text{source terms}.
$$

Here $W_{ijkl}$ is the Weyl tensor of the boundary metric and $E_4$ is the Euler density. The coefficient of $\Box R$ is scheme dependent: it can be shifted by adding a finite local $R^2$ counterterm. The coefficients $a$ and $c$ are genuine CFT data. For CFTs dual to two-derivative Einstein gravity in AdS$_5$,

$$
a=c=\frac{\pi L^3}{8G_5}.
$$

For $\mathcal N=4$ $SU(N)$ SYM at large $N$, this gives $a=c\sim N^2/4$, with the precise finite-$N$ field-theory answer depending on the choice of $SU(N)$ versus $U(N)$ gauge group.

## Anomalies are local, vevs are not

A common structural point is worth emphasizing. The anomaly density $\mathcal A$ is local in the sources:

$$
\mathcal A=\mathcal A[g_{ij},A_i,\lambda].
$$

It is determined by the asymptotic expansion. It does not depend on the choice of thermal state, the presence of a black hole horizon, or other deep-interior data.

By contrast, one-point functions such as

$$
\langle T_{ij}\rangle,
\qquad
\langle J_i\rangle,
\qquad
\langle\mathcal O_I\rangle
$$

usually contain nonlocal state-dependent data. For example, the energy density of a black brane is not fixed by the boundary metric alone. It is determined by the normalizable part of the bulk solution, which knows about the horizon.

Thus holographic renormalization separates two kinds of data:

| Data | Character | Determined by |
|---|---|---|
| Divergences | local | near-boundary sources |
| Counterterms | local | covariance and asymptotic equations |
| Anomalies | local | logarithmic terms |
| Vevs | generally nonlocal | full bulk solution and interior condition |

This separation is one reason the formalism is so powerful.

## Ward identities as consistency conditions

Suppose a bulk solution is claimed to describe a boundary state with sources $g_{ij}$, $A_i$, and $\lambda$. After holographic renormalization, its one-point functions must satisfy

$$
D_i\langle J_a^i\rangle
=
-\langle\mathcal O_I\rangle(T_a\lambda)^I,
$$

$$
\nabla_i\langle T^i{}_{j}\rangle
=
F_{ji}^a\langle J_a^i\rangle
+
\langle\mathcal O_I\rangle\partial_j\lambda^I,
$$

and

$$
\langle T^i{}_{i}\rangle
=
\sum_I(d-\Delta_I)\lambda^I\langle\mathcal O_I\rangle
+
\mathcal A.
$$

These equations are especially useful in numerical holography. They are gauge-invariant checks on the solution and on the boundary extraction of physical quantities.

For example, in a static black brane with flat boundary metric, constant scalar sources, and a time component $A_t(z)$ whose boundary value is a constant chemical potential $\mu$, the boundary field strength vanishes:

$$
F_{ij}=0.
$$

The diffeomorphism Ward identity then says

$$
\partial_i\langle T^i{}_{j}\rangle=0.
$$

The state may have nonzero energy density, pressure, charge density, and entropy density, but a constant chemical potential does not by itself apply a force.

If instead one turns on an electric field $E_i=F_{ti}$, the Ward identity includes the work done by the electric field on the current.

## Scheme dependence

Finite local counterterms can shift one-point functions by local functions of the sources. For instance, in four boundary dimensions a finite counterterm

$$
S_{\rm finite}\supset
\alpha\int d^4x\sqrt g\,R^2
$$

shifts the stress tensor by a local curvature expression. It also shifts the coefficient of the $\Box R$ term in the trace anomaly.

This is not a bug. It is the usual renormalization-scheme dependence of local contact terms. Nonlocal separated-point correlators and scheme-independent anomaly coefficients such as $a$ and $c$ are not changed by these local redefinitions.

The practical rule is:

$$
\boxed{
\text{do not assign invariant meaning to local contact terms until the scheme is specified.}
}
$$

This point will reappear when we compute correlation functions beyond two points.

## Dictionary checkpoint

The Ward-identity dictionary is:

| Boundary statement | Bulk statement |
|---|---|
| gauge Ward identity | radial Gauss constraint |
| stress-tensor Ward identity | radial momentum constraint |
| trace/local RG identity | radial Hamiltonian constraint |
| conformal anomaly | logarithmic counterterm |
| explicit source breaking | nonzero source term in Ward identity |
| scheme dependence | finite local counterterm ambiguity |

The central lesson is that holographic renormalization does not merely make quantities finite. It organizes the boundary symmetries of the CFT as constraints of the bulk gravitational system.

## Common confusions

### “The stress tensor is always conserved.”

The correct statement is that the total system is conserved. If the QFT is coupled to nondynamical external sources, the QFT stress tensor alone can exchange energy and momentum with those sources. This is why

$$
\nabla_i\langle T^i{}_{j}\rangle
=
F_{ji}\langle J^i\rangle
+
\langle\mathcal O\rangle\partial_j\lambda
$$

is perfectly consistent.

### “A conformal field theory always has traceless stress tensor.”

In flat space with no dimensionful sources and no anomaly, yes. On curved backgrounds in even dimension, a Weyl anomaly can make the trace nonzero. Relevant deformations also give a nonzero trace through explicit breaking.

### “The anomaly depends on the state.”

The anomaly is local in the sources. It is not determined by the black hole horizon, the temperature, or other normalizable data. The vev can be state dependent; the anomaly is not.

### “All anomaly terms are scheme independent.”

No. Some local terms can be shifted by finite local counterterms. In four dimensions, the $\Box R$ term in the trace anomaly is scheme dependent, while the $a$ and $c$ coefficients are invariant CFT data.

### “The Hamiltonian constraint is just another equation of motion.”

It is more special. In radial Hamiltonian language it generates radial reparametrizations. Near the boundary, it becomes the local Weyl/RG identity of the boundary theory.

## Exercises

### Exercise 1: Gauge Ward identity with a charged source

Assume

$$
\delta_\alpha A_i=D_i\alpha,
\qquad
\delta_\alpha\lambda=-iq\alpha\lambda,
\qquad
\delta_\alpha\lambda^*=iq\alpha\lambda^*.
$$

The variation of the generating functional contains

$$
\delta W
=
\int\sqrt g
\left(
\langle J^i\rangle\delta A_i
+
\langle\mathcal O\rangle\delta\lambda
+
\langle\mathcal O^*\rangle\delta\lambda^*
\right).
$$

Derive the Ward identity.

<details>
<summary><strong>Solution</strong></summary>

Substitute the transformations:

$$
\delta W
=
\int\sqrt g
\left(
\langle J^i\rangle D_i\alpha
-iq\alpha\lambda\langle\mathcal O\rangle
+iq\alpha\lambda^*\langle\mathcal O^*\rangle
\right).
$$

Integrating the first term by parts gives

$$
\delta W
=
-\int\sqrt g\,\alpha
\left(
D_i\langle J^i\rangle
+iq\lambda\langle\mathcal O\rangle
-iq\lambda^*\langle\mathcal O^*\rangle
\right).
$$

Gauge invariance for arbitrary $\alpha(x)$ gives

$$
D_i\langle J^i\rangle
=
-iq\lambda\langle\mathcal O\rangle
+iq\lambda^*\langle\mathcal O^*\rangle.
$$

If the charged source vanishes, this reduces to current conservation.

</details>

### Exercise 2: Diffeomorphism Ward identity without gauge fields

Set $A_i=0$ and consider one scalar source $\lambda(x)$. Using

$$
\delta_\xi g_{ij}=\nabla_i\xi_j+\nabla_j\xi_i,
\qquad
\delta_\xi\lambda=\xi^j\partial_j\lambda,
$$

show that

$$
\nabla_i\langle T^i{}_{j}\rangle
=
\langle\mathcal O\rangle\partial_j\lambda.
$$

<details>
<summary><strong>Solution</strong></summary>

The diffeomorphism variation is

$$
\delta_\xi W
=
\int\sqrt g
\left(
\frac12\langle T^{ij}\rangle(\nabla_i\xi_j+\nabla_j\xi_i)
+
\langle\mathcal O\rangle\xi^j\partial_j\lambda
\right).
$$

Since $\langle T^{ij}\rangle$ is symmetric,

$$
\frac12\langle T^{ij}\rangle(\nabla_i\xi_j+\nabla_j\xi_i)
=
\langle T^{ij}\rangle\nabla_i\xi_j.
$$

Integrating by parts,

$$
\delta_\xi W
=
\int\sqrt g\,\xi^j
\left(
-\nabla_i\langle T^i{}_{j}\rangle
+
\langle\mathcal O\rangle\partial_j\lambda
\right).
$$

Diffeomorphism invariance for arbitrary $\xi^j$ gives

$$
\nabla_i\langle T^i{}_{j}\rangle
=
\langle\mathcal O\rangle\partial_j\lambda.
$$

</details>

### Exercise 3: Trace identity for a relevant deformation

A $d$-dimensional CFT is deformed by

$$
\delta S=\int d^d x\sqrt g\,\lambda\mathcal O,
$$

where $\mathcal O$ has dimension $\Delta<d$. Ignore the Weyl anomaly. What is the trace Ward identity?

<details>
<summary><strong>Solution</strong></summary>

The source has Weyl weight $\Delta-d$:

$$
\delta_\sigma\lambda=(\Delta-d)\sigma\lambda.
$$

Weyl invariance of the deformed generating functional gives

$$
0=
\int\sqrt g\,\sigma
\left(
\langle T^i{}_{i}\rangle
+(\Delta-d)\lambda\langle\mathcal O\rangle
\right).
$$

Therefore

$$
\langle T^i{}_{i}\rangle
=(d-\Delta)\lambda\langle\mathcal O\rangle.
$$

The deformation explicitly breaks scale invariance because $\lambda$ has positive mass dimension $d-\Delta$.

</details>

### Exercise 4: Integrated two-dimensional anomaly

For a two-dimensional CFT on a compact Euclidean surface with no boundary,

$$
\langle T^i{}_{i}\rangle=\frac{c}{24\pi}R.
$$

Use the Gauss–Bonnet theorem

$$
\int d^2x\sqrt g\,R=4\pi\chi
$$

to compute the integrated trace.

<details>
<summary><strong>Solution</strong></summary>

Integrating the anomaly gives

$$
\int d^2x\sqrt g\,\langle T^i{}_{i}\rangle
=
\frac{c}{24\pi}
\int d^2x\sqrt g\,R.
$$

Using Gauss–Bonnet,

$$
\int d^2x\sqrt g\,\langle T^i{}_{i}\rangle
=
\frac{c}{24\pi}(4\pi\chi)
=
\frac{c}{6}\chi.
$$

For a sphere, $\chi=2$, so the integrated trace is $c/3$.

</details>

## Further reading

- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- D. Martelli and W. Mueck, [Holographic Renormalization and Ward Identities with the Hamilton–Jacobi Method](https://arxiv.org/abs/hep-th/0205061).
