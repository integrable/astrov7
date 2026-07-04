---
title: "Radial Hamiltonian Viewpoint"
description: "Holographic renormalization as a radial Hamilton-Jacobi problem, with the AdS radial direction acting as scale evolution and the Hamiltonian constraint becoming the local RG equation."
sidebar:
  order: 60
---

Holographic renormalization can be done by expanding fields near the boundary and adding counterterms by hand. That method is concrete and efficient. But it can feel like a long list of subtractions.

The radial Hamiltonian viewpoint explains the structure behind the subtractions. Treat the AdS radial coordinate as a Hamiltonian evolution parameter. The induced fields on a cutoff surface are canonical coordinates. Their radial derivatives determine canonical momenta. The on-shell action as a functional of cutoff data obeys a Hamilton–Jacobi equation. The divergent counterterms are the local asymptotic solution of that Hamilton–Jacobi equation.

The slogan is

$$
\boxed{
\text{holographic renormalization}
=
\text{asymptotic Hamilton–Jacobi theory in the radial direction}.}
$$

This page is more conceptual than computational, but it is a very useful organizing principle. It explains why the radial constraints give Ward identities, why counterterms are local, why logarithmic terms give anomalies, and why the radial direction is naturally interpreted as an energy scale.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A radial foliation of asymptotically AdS spacetime. The induced metric and fields on radial slices are canonical data. Their momenta are variations of the cutoff on-shell action. The Hamilton-Jacobi equation determines local divergent terms, counterterms, and the boundary local RG equation.](/figures/course/radial-hamiltonian-viewpoint.svg)

<figcaption>

The radial Hamiltonian picture. A cutoff surface $\Sigma_\epsilon$ carries induced fields $\gamma_{ij}$ and $\phi$. Their conjugate momenta are variations of the cutoff on-shell action $S_z$. The Hamilton–Jacobi constraint determines the local divergent part of $S_z$, whose negative is the counterterm action. The finite nonlocal part becomes the renormalized CFT generating functional.

</figcaption>
</figure>

## Why this matters

The previous pages introduced three facts:

1. the on-shell action diverges near the AdS boundary;
2. the divergences are removed by local counterterms;
3. the renormalized one-point functions obey Ward identities.

The radial Hamiltonian viewpoint explains all three at once.

Near the boundary, radial evolution is asymptotically the same as a Weyl rescaling of the boundary data. A radial cutoff $z=\epsilon$ therefore behaves like a UV cutoff in the boundary field theory:

$$
\mu\sim \frac1\epsilon.
$$

Changing the cutoff is a version of RG evolution. The local divergent part of the on-shell action is determined by the short-distance behavior of the theory, so it must be a local functional of the induced fields. The finite nonlocal part is not determined by the asymptotic expansion alone; it contains state-dependent vev data.

This page turns that intuition into equations.

## Radial foliation

Let the bulk dimension be $d+1$. Choose a radial coordinate $r$ or $z$ and foliate the spacetime by hypersurfaces $\Sigma_z$ of constant radial coordinate. A general radial ADM decomposition is

$$
ds^2
=
N^2dz^2
+
\gamma_{ij}(dx^i+N^i dz)(dx^j+N^j dz).
$$

Here:

| Quantity | Meaning |
|---|---|
| $N$ | radial lapse |
| $N^i$ | radial shift |
| $\gamma_{ij}$ | induced metric on $\Sigma_z$ |
| $D_i$ | covariant derivative built from $\gamma_{ij}$ |

Fefferman–Graham gauge is the special choice

$$
N=\frac{L}{z},
\qquad
N^i=0,
\qquad
\gamma_{ij}=\frac{L^2}{z^2}g_{ij}(z,x).
$$

The extrinsic curvature of the slice is

$$
K_{ij}
=
\frac{1}{2N}
\left(
\dot\gamma_{ij}-D_iN_j-D_jN_i
\right),
$$

where a dot denotes $\partial_z$.

For pure AdS in Fefferman–Graham gauge,

$$
\gamma_{ij}=\frac{L^2}{z^2}g_{(0)ij},
$$

so radial motion changes the overall Weyl factor of the induced metric. This is the geometric reason why radial evolution is tied to scale evolution.

## Canonical momenta

For Einstein gravity coupled to matter, the radial canonical momentum conjugate to $\gamma_{ij}$ is proportional to the Brown–York tensor before counterterms. With action normalization

$$
S_{\rm grav}
=
\frac{1}{2\kappa^2}
\int d^{d+1}x\sqrt G\,(R-2\Lambda)
+
\frac{1}{\kappa^2}
\int_{\partial M}d^dx\sqrt\gamma\,K,
$$

one has schematically

$$
\pi^{ij}
=
\frac{\delta S_{\rm reg}}{\delta\gamma_{ij}}
\sim
\frac{\sqrt\gamma}{2\kappa^2}
\left(K^{ij}-K\gamma^{ij}\right),
$$

with signs depending on the orientation of the radial normal and on whether the cutoff surface is treated as an inner or outer boundary.

For a scalar field with action

$$
S_\phi
=\frac12\int d^{d+1}x\sqrt G
\left(G^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right),
$$

the radial canonical momentum is

$$
\Pi_\phi
=
\frac{\delta S_{\rm reg}}{\delta\phi}
=
\sqrt\gamma\,n^M\partial_M\phi,
$$

again up to the sign convention for the outward normal $n^M$.

The renormalized momenta are obtained by adding the variation of the counterterm action:

$$
\pi^{ij}_{\rm ren}
=
\lim_{\epsilon\to0}
\left(\pi^{ij}_{\rm reg}+\pi^{ij}_{\rm ct}\right),
$$

$$
\Pi_{\phi,\rm ren}
=
\lim_{\epsilon\to0}
\left(\Pi_{\phi,\rm reg}+\Pi_{\phi,\rm ct}\right).
$$

These finite momenta are the holographic one-point functions:

$$
\pi^{ij}_{\rm ren}
\longleftrightarrow
\frac12\sqrt{g_{(0)}}\langle T^{ij}\rangle,
\qquad
\Pi_{\phi,\rm ren}
\longleftrightarrow
\sqrt{g_{(0)}}\langle\mathcal O\rangle.
$$

This is the canonical version of the source-response dictionary.

## The cutoff on-shell action

Fix the induced fields on a cutoff surface $\Sigma_z$:

$$
\gamma_{ij}(z,x),
\qquad
\phi(z,x),
\qquad
A_i(z,x),
\ldots
$$

Solve the bulk equations inward subject to an interior condition: regularity in Euclidean signature, infalling behavior at a Lorentzian horizon, or normalizability in global AdS. Evaluate the action on that solution. The result is a functional of the cutoff data:

$$
S_z[\gamma,\phi,A,\ldots].
$$

Hamilton–Jacobi theory says that the canonical momenta are functional derivatives of this on-shell action:

$$
\pi^{ij}(z,x)
=
\frac{\delta S_z}{\delta\gamma_{ij}(x)},
$$

$$
\Pi_\phi(z,x)
=
\frac{\delta S_z}{\delta\phi(x)},
$$

and similarly for other fields.

Thus $S_z$ is Hamilton's principal function for radial evolution.

## Hamiltonian constraints

Because the bulk theory is diffeomorphism invariant, radial evolution is constrained. In radial Hamiltonian form, the action takes the schematic form

$$
S
=
\int dz\,d^dx
\left(
\pi^{ij}\dot\gamma_{ij}
+
\Pi_\phi\dot\phi
+
\Pi_A^i\dot A_i
-
N\mathcal H
-N^i\mathcal H_i
-A_z\mathcal G
\right).
$$

The lapse $N$, shift $N^i$, and radial gauge field component $A_z$ act as Lagrange multipliers. Their equations of motion impose constraints:

$$
\mathcal H=0,
\qquad
\mathcal H_i=0,
\qquad
\mathcal G=0.
$$

These are the Hamiltonian, momentum, and Gauss constraints.

Replacing canonical momenta by functional derivatives of $S_z$ gives the Hamilton–Jacobi equations:

$$
\mathcal H\!\left(
\gamma,
\phi,
A,
\frac{\delta S_z}{\delta\gamma},
\frac{\delta S_z}{\delta\phi},
\frac{\delta S_z}{\delta A}
\right)=0,
$$

$$
\mathcal H_i\!\left(
\gamma,
\phi,
A,
\frac{\delta S_z}{\delta\gamma},
\frac{\delta S_z}{\delta\phi},
\frac{\delta S_z}{\delta A}
\right)=0,
$$

$$
\mathcal G\!\left(
A,
\phi,
\frac{\delta S_z}{\delta A},
\frac{\delta S_z}{\delta\phi}
\right)=0.
$$

These are functional differential equations for the cutoff on-shell action.

The key point is that their divergent asymptotic solution is local. That local solution is exactly what counterterms subtract.

## A schematic form of the Hamiltonian constraint

For pure Einstein gravity with negative cosmological constant, the Hamiltonian constraint has the form

$$
\mathcal H_{\rm grav}
=
\frac{2\kappa^2}{\sqrt\gamma}
\left(
\pi_{ij}\pi^{ij}
-
\frac{1}{d-1}\pi^2
\right)
-
\frac{\sqrt\gamma}{2\kappa^2}
\left(
R[\gamma]+\frac{d(d-1)}{L^2}
\right)
=0,
$$

up to sign conventions for the radial normal and the definition of $K_{ij}$.

After replacing

$$
\pi^{ij}=\frac{\delta S_z}{\delta\gamma_{ij}},
$$

this becomes a nonlinear functional equation for $S_z[\gamma]$.

With matter fields, additional terms appear. For a scalar,

$$
\mathcal H_\phi
\sim
\frac{1}{2\sqrt\gamma}\Pi_\phi^2
-
\frac12\sqrt\gamma
\left(
\gamma^{ij}\partial_i\phi\partial_j\phi+m^2\phi^2
\right),
$$

again with convention-dependent signs. The important structural point is not the exact sign in this schematic formula, but that the Hamiltonian constraint relates radial momenta to local functions of induced fields.

## Local divergent solution

Near the boundary, the cutoff on-shell action has the structure

$$
S_z[\gamma,\phi]
=
S_{\rm div}^{\rm local}[\gamma,\phi;z]
+
S_{\log}[\gamma,\phi;z]
+
\Gamma[\gamma_{(0)},\lambda]
+
\cdots.
$$

Here:

| Term | Meaning |
|---|---|
| $S_{\rm div}^{\rm local}$ | local power-law divergences |
| $S_{\log}$ | local logarithmic divergence, if present |
| $\Gamma$ | finite nonlocal renormalized generating functional |
| $\cdots$ | terms vanishing as the cutoff is removed |

The counterterm action is chosen as

$$
S_{\rm ct}
=
-S_{\rm div}^{\rm local}-S_{\log}.
$$

Then

$$
S_{\rm ren}
=
\lim_{z\to0}(S_z+S_{\rm ct})
=
\Gamma
+
\text{finite local scheme terms}.
$$

This equation is the radial Hamiltonian explanation of holographic renormalization.

The divergent terms are local because they are determined by asymptotic radial evolution. The finite nonlocal piece $\Gamma$ is not determined locally: it depends on the global solution and the interior boundary condition.

## Dilatation operator

Near the AdS boundary, radial evolution is approximately a scale transformation. In Fefferman–Graham coordinates,

$$
\gamma_{ij}(z,x)
\sim
\frac{L^2}{z^2}g_{(0)ij}(x),
$$

so

$$
z\partial_z\gamma_{ij}\sim -2\gamma_{ij}.
$$

For a scalar field dual to an operator of dimension $\Delta$,

$$
\phi(z,x)
\sim
z^{d-\Delta}\lambda(x),
$$

so

$$
z\partial_z\phi
\sim
(d-\Delta)\phi.
$$

It is useful to introduce the dilatation operator

$$
\delta_D
=
\int d^dx
\left(
2\gamma_{ij}\frac{\delta}{\delta\gamma_{ij}}
+
(\Delta-d)\phi\frac{\delta}{\delta\phi}
+\cdots
\right).
$$

Then near the boundary,

$$
z\partial_z
\simeq
-\delta_D.
$$

This relation is the technical bridge between radial evolution and the renormalization group.

The ellipsis includes the corresponding weights for gauge fields, spinors, and other sources. For a background gauge field sourcing a conserved current, $A_i$ is usually treated as a one-form source of Weyl weight zero in the local RG equation.

## Counterterms by dilatation weight

The Hamilton–Jacobi method often organizes the local action by dilatation weight:

$$
S_{\rm loc}
=
S_{(0)}+S_{(2)}+S_{(4)}+\cdots+S_{(d)}+S_{\log}+\cdots.
$$

The subscript indicates the number of derivatives, or more generally the dilatation weight. For pure gravity, the first terms have the schematic form

$$
S_{(0)}
\sim
\int d^dx\sqrt\gamma,
$$

$$
S_{(2)}
\sim
\int d^dx\sqrt\gamma\,R[\gamma],
$$

$$
S_{(4)}
\sim
\int d^dx\sqrt\gamma
\left(
R_{ij}R^{ij},
R^2
\right),
$$

and so on.

Inserting this expansion into the Hamilton–Jacobi equation determines the coefficients recursively. One does not need the full bulk solution to determine these terms. The asymptotic equations are enough.

For example, in asymptotically AdS gravity, the leading gravitational counterterm is proportional to the volume of the cutoff surface:

$$
S_{\rm ct}^{(0)}
\propto
\int d^dx\sqrt\gamma.
$$

The next counterterm is proportional to the intrinsic curvature:

$$
S_{\rm ct}^{(2)}
\propto
\int d^dx\sqrt\gamma\,R[\gamma].
$$

These are exactly the terms one finds by explicitly evaluating the near-boundary divergences of the regulated action.

## A scalar example

For a scalar with standard quantization and dimension $\Delta>d/2$, the leading asymptotic behavior is

$$
\phi(z,x)=z^{d-\Delta}\lambda(x)+\cdots.
$$

The raw scalar canonical momentum behaves as

$$
\Pi_\phi
\sim
\sqrt\gamma\,n^z\partial_z\phi.
$$

Because

$$
\sqrt\gamma\sim z^{-d},
\qquad
n^z\partial_z\phi\sim (d-\Delta)z^{d-\Delta},
$$

the momentum diverges like

$$
\Pi_\phi
\sim
(d-\Delta)z^{-\Delta}\lambda+\cdots.
$$

A local quadratic counterterm cancels this leading divergence:

$$
S_{\rm ct}^{\phi^2}
\sim
\frac{d-\Delta}{2L}
\int_{\Sigma_z}d^dx\sqrt\gamma\,\phi^2,
$$

up to the sign convention for the radial normal and Euclidean action. Derivative counterterms such as

$$
\int\sqrt\gamma\,\gamma^{ij}\partial_i\phi\partial_j\phi
$$

cancel subleading divergences when they occur.

The Hamilton–Jacobi method determines these counterterms without solving the full bulk wave equation at finite $z$. It solves for the local divergent part of $S_z$.

## The local RG equation

Once the counterterms are subtracted, the finite generating functional satisfies a local RG identity. In a simple notation,

$$
\left(
2g_{ij}\frac{\delta}{\delta g_{ij}}
+
\beta^I(\lambda)\frac{\delta}{\delta\lambda^I}
\right)
W_{\rm ren}
=
\int d^dx\sqrt g\,\mathcal A.
$$

At a conformal fixed point with a source for an operator of dimension $\Delta_I$,

$$
\beta^I(\lambda)
=
(\Delta_I-d)\lambda^I+\cdots.
$$

If all sources for relevant or irrelevant operators are set to zero and there is no anomaly, the identity reduces to Weyl invariance:

$$
2g_{ij}\frac{\delta W_{\rm ren}}{\delta g_{ij}}=0.
$$

Using the definition of the stress tensor, this becomes

$$
\langle T^i{}_{i}\rangle=0.
$$

If the anomaly is present,

$$
2g_{ij}\frac{\delta W_{\rm ren}}{\delta g_{ij}}
=
\int d^dx\sqrt g\,\mathcal A,
$$

which is the integrated version of

$$
\langle T^i{}_{i}\rangle=\mathcal A.
$$

Thus the radial Hamiltonian constraint is the bulk origin of the local Callan–Symanzik equation.

## Momentum and Gauss constraints revisited

The Hamiltonian constraint gives the trace/local RG identity. The other constraints give the remaining Ward identities.

The momentum constraint is the generator of diffeomorphisms along $\Sigma_z$. In Hamilton–Jacobi form, it says that $S_z$ is invariant under boundary diffeomorphisms, provided all induced fields transform correctly. In renormalized form this becomes

$$
\nabla_i\langle T^i{}_{j}\rangle
=
F_{ji}^a\langle J_a^i\rangle
+
\langle\mathcal O_I\rangle\partial_j\lambda^I.
$$

The Gauss constraint is the generator of gauge transformations on $\Sigma_z$. In renormalized form it becomes

$$
D_i\langle J_a^i\rangle
=
-\langle\mathcal O_I\rangle(T_a\lambda)^I.
$$

The previous page derived these identities from boundary symmetries. The radial Hamiltonian viewpoint shows why they are guaranteed by bulk constraints.

## What is determined locally?

The Hamilton–Jacobi equation is a functional equation. One might hope that solving it near the boundary determines everything. It does not.

It determines the local divergent part of the on-shell action:

$$
S_{\rm div}^{\rm local}+S_{\log}.
$$

It also determines local relations among coefficients in the Fefferman–Graham expansion. But it does not determine the finite nonlocal functional $\Gamma$ from near-boundary data alone.

That finite functional contains the physical state-dependent data:

$$
\langle T_{ij}\rangle,
\qquad
\langle J_i\rangle,
\qquad
\langle\mathcal O\rangle.
$$

To determine these, one must solve the bulk problem with an interior condition. In Euclidean signature, this often means smoothness in the interior. In Lorentzian black-hole backgrounds, retarded correlators require infalling boundary conditions at the horizon.

This is the sharp version of a recurring theme:

$$
\boxed{
\text{sources determine local asymptotics; states determine normalizable data.}
}
$$

## Relation to Wilsonian RG

The radial Hamiltonian viewpoint is close in spirit to Wilsonian RG, but it is not identical to a literal Wilsonian integration of boundary modes.

The radial cutoff $z=\epsilon$ corresponds roughly to a boundary UV cutoff $\mu\sim1/\epsilon$. Moving the cutoff inward removes access to short-distance boundary data. However, a radial slice in classical gravity also carries canonical momenta. To specify radial evolution one needs both coordinates and momenta, or equivalently sources and responses.

This is why holographic RG has two complementary forms:

| Viewpoint | Object evolved |
|---|---|
| Hamilton–Jacobi holographic renormalization | on-shell action as a functional of induced fields |
| Wilsonian holographic RG | effective action at a finite radial cutoff |
| Fefferman–Graham expansion | asymptotic source and vev coefficients |

This course mostly uses the Hamilton–Jacobi viewpoint as a structural explanation for counterterms and Ward identities. Later applications may use finite-cutoff ideas more explicitly.

## Example: radial flow and beta functions

Consider a domain-wall-like metric

$$
ds^2=dr^2+e^{2A(r)}g_{ij}dx^idx^j
$$

and scalar fields $\phi^I(r)$. In many holographic RG flow solutions, the radial evolution of scalars can be interpreted as running couplings.

A natural holographic beta function is

$$
\beta^I
=
\frac{d\phi^I}{dA}.
$$

Near a fixed point, where $A\sim r/L$ and

$$
\phi^I\sim e^{-(d-\Delta_I)r/L}\lambda^I,
$$

one obtains

$$
\beta^I
\sim
(\Delta_I-d)\phi^I.
$$

This is the expected linearized beta function for a source coupling to an operator of dimension $\Delta_I$.

One should not overinterpret this formula. In a general holographic RG flow, identifying bulk scalar profiles with field-theory running couplings can be scheme dependent. But near an AdS fixed point, the scaling is robust and is exactly the same scaling that appears in the trace Ward identity.

## The role of finite counterterms

The Hamilton–Jacobi equation determines divergent local terms. Finite local terms are not fixed by cancellation of divergences. They correspond to scheme choices:

$$
S_{\rm ren}
\longrightarrow
S_{\rm ren}+S_{\rm finite}^{\rm local}.
$$

This changes one-point functions by local expressions in the sources and changes contact terms in correlators. It does not change nonlocal separated-point correlators or scheme-independent anomaly coefficients.

In Hamilton–Jacobi language, finite local terms are finite canonical transformations. They redefine the renormalized momenta without changing the underlying bulk solution.

This is a helpful way to think about scheme dependence: the phase-space variables can be locally reparametrized at the boundary.

## Practical algorithm

For a standard holographic renormalization calculation, the radial Hamiltonian method gives the following workflow:

1. Choose a radial foliation and induced fields $\gamma_{ij}$, $\phi$, $A_i$, and so on.
2. Write the radial canonical momenta.
3. Express the Hamiltonian, momentum, and Gauss constraints.
4. Replace momenta by functional derivatives of $S_z$.
5. Solve the Hamilton–Jacobi equations asymptotically by local covariant terms.
6. Identify the divergent local action $S_{\rm div}^{\rm local}+S_{\log}$.
7. Add $S_{\rm ct}= -S_{\rm div}^{\rm local}-S_{\log}$.
8. Vary $S_{\rm ren}$ to obtain finite momenta and one-point functions.
9. Check the Ward identities.

In practice, one often uses a hybrid method: solve the near-boundary field equations directly, infer the counterterms, and use the Hamiltonian constraints as checks. The Hamilton–Jacobi viewpoint explains why that hybrid method works.

## Dictionary checkpoint

The radial Hamiltonian dictionary is:

| Bulk radial Hamiltonian object | Boundary interpretation |
|---|---|
| radial coordinate $z$ | inverse energy scale, $\mu^{-1}$ |
| induced metric $\gamma_{ij}$ | cutoff version of metric source |
| induced scalar $\phi$ | cutoff version of scalar source |
| canonical momentum $\Pi_\phi$ | cutoff one-point function |
| renormalized momentum | renormalized vev |
| Hamilton–Jacobi equation | local RG equation |
| momentum constraint | diffeomorphism Ward identity |
| Gauss constraint | current Ward identity |
| logarithmic HJ term | Weyl anomaly |
| finite local boundary term | renormalization scheme choice |

The most important conceptual point is that counterterms are not arbitrary decorations added to the on-shell action. They are the local divergent solution of radial Hamilton–Jacobi theory.

## Common confusions

### “The radial direction is physical time.”

No. The radial coordinate is treated as Hamiltonian time in a mathematical decomposition of the bulk equations. It is not the Lorentzian time of the boundary QFT. In AdS/CFT, radial evolution is tied to scale evolution, while boundary time evolution is generated by the CFT Hamiltonian.

### “The Hamilton–Jacobi equation determines the full CFT generating functional.”

Not by itself. The local divergent part is determined asymptotically. The finite nonlocal part depends on the full bulk solution and the interior condition. This is where state and dynamics enter.

### “Radial RG is exactly Wilsonian RG.”

It is closely related, but not identical without further work. A radial cutoff gives a natural scale separation, yet the bulk phase-space structure includes both fields and momenta. A fully Wilsonian interpretation requires specifying how boundary conditions and finite-cutoff actions are treated.

### “Finite counterterms are mistakes.”

Finite local counterterms are allowed scheme choices. They change contact terms and local pieces of one-point functions but do not change scheme-independent physical data.

### “The anomaly is produced by the finite nonlocal action.”

The anomaly is local and is tied to the logarithmic counterterm. The finite nonlocal action contains state-dependent and dynamical information, but the anomaly density is determined by local asymptotic data.

## Exercises

### Exercise 1: Radial scaling of the induced metric

In Fefferman–Graham coordinates,

$$
ds^2=\frac{L^2}{z^2}(dz^2+g_{ij}(z,x)dx^idx^j),
$$

with $g_{ij}(z,x)\to g_{(0)ij}(x)$ near the boundary. Show that the induced metric obeys

$$
z\partial_z\gamma_{ij}\sim -2\gamma_{ij}
$$

near $z=0$.

<details>
<summary><strong>Solution</strong></summary>

The induced metric on $z={\rm constant}$ slices is

$$
\gamma_{ij}(z,x)=\frac{L^2}{z^2}g_{ij}(z,x).
$$

Near the boundary, $g_{ij}(z,x)=g_{(0)ij}(x)+\cdots$, so the leading radial dependence is $z^{-2}$. Therefore

$$
z\partial_z\gamma_{ij}
=
z\partial_z\left(\frac{L^2}{z^2}g_{(0)ij}+\cdots\right)
=
-2\frac{L^2}{z^2}g_{(0)ij}+\cdots
\sim
-2\gamma_{ij}.
$$

This is why radial evolution near the boundary acts like a Weyl transformation.

</details>

### Exercise 2: Leading scalar momentum divergence

A scalar behaves near the boundary as

$$
\phi(z,x)=z^{d-\Delta}\lambda(x)+\cdots.
$$

Using $\sqrt\gamma\sim z^{-d}$ and $n^z\partial_z\sim z\partial_z/L$, estimate the leading divergence of

$$
\Pi_\phi=\sqrt\gamma\,n^z\partial_z\phi.
$$

<details>
<summary><strong>Solution</strong></summary>

First,

$$
z\partial_z\phi
=
(d-\Delta)z^{d-\Delta}\lambda+\cdots.
$$

Since $n^z\partial_z\sim z\partial_z/L$,

$$
n^z\partial_z\phi
\sim
\frac{d-\Delta}{L}z^{d-\Delta}\lambda.
$$

Multiplying by $\sqrt\gamma\sim z^{-d}$ gives

$$
\Pi_\phi
\sim
\frac{d-\Delta}{L}z^{-\Delta}\lambda.
$$

The momentum diverges as $z^{-\Delta}$, so a local counterterm proportional to $\int\sqrt\gamma\,\phi^2$ is needed to cancel the leading divergence.

</details>

### Exercise 3: Trace identity from local RG

Assume

$$
\left(
2g_{ij}\frac{\delta}{\delta g_{ij}}
+(\Delta-d)\lambda\frac{\delta}{\delta\lambda}
\right)W
=0.
$$

Using

$$
\delta W
=
\int\sqrt g
\left(
\frac12\langle T^{ij}\rangle\delta g_{ij}
+
\langle\mathcal O\rangle\delta\lambda
\right),
$$

derive the trace Ward identity.

<details>
<summary><strong>Solution</strong></summary>

The functional derivatives are

$$
\frac{\delta W}{\delta g_{ij}}
=
\frac12\sqrt g\,\langle T^{ij}\rangle,
$$

and

$$
\frac{\delta W}{\delta\lambda}
=
\sqrt g\,\langle\mathcal O\rangle.
$$

Substituting into the local RG equation gives

$$
2g_{ij}\left(\frac12\sqrt g\,\langle T^{ij}\rangle\right)
+(\Delta-d)\lambda\sqrt g\,\langle\mathcal O\rangle=0.
$$

Dividing by $\sqrt g$,

$$
\langle T^i{}_{i}\rangle
+(\Delta-d)\lambda\langle\mathcal O\rangle=0.
$$

Thus

$$
\langle T^i{}_{i}\rangle
=(d-\Delta)\lambda\langle\mathcal O\rangle.
$$

</details>

### Exercise 4: Why logarithms imply anomalies

Suppose a regulated generating functional contains a local term

$$
W_{\log}=C\log(\epsilon\mu),
$$

where $C$ is a local functional of the sources. Explain why this term leads to scale dependence after the cutoff divergence is subtracted.

<details>
<summary><strong>Solution</strong></summary>

The divergent dependence on $\epsilon$ is removed by a counterterm. However, the logarithm contains both $\epsilon$ and the arbitrary renormalization scale $\mu$:

$$
\log(\epsilon\mu)=\log\epsilon+\log\mu.
$$

Canceling the $\log\epsilon$ divergence leaves a finite dependence on $\log\mu$. Therefore

$$
\mu\frac{dW_{\rm ren}}{d\mu}
$$

is nonzero and equal, up to sign conventions, to the local coefficient $C$. In a CFT this local scale dependence is the Weyl anomaly.

</details>

## Further reading

- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- D. Martelli and W. Mueck, [Holographic Renormalization and Ward Identities with the Hamilton–Jacobi Method](https://arxiv.org/abs/hep-th/0205061).
- I. Papadimitriou, [Lectures on Holographic Renormalization](https://arxiv.org/abs/1608.06211).
