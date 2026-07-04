---
title: "Covariant HRT formula"
description: "The Hubeny-Rangamani-Takayanagi formula for holographic entanglement entropy in time-dependent AdS/CFT states."
sidebar:
  order: 30
---

The Ryu–Takayanagi formula is easiest to state when the bulk spacetime is static and the boundary region $A$ lies on a time-reflection-symmetric slice. But real states evolve. Black holes form. Shells collapse. Entanglement spreads after quenches. Boundary regions can be specified on arbitrary Cauchy slices. In those situations there is usually no preferred bulk time slice on which to minimize area.

The covariant replacement is the Hubeny–Rangamani–Takayanagi formula, usually called the **HRT formula**. It says that the entropy of a boundary region is computed by the area of a bulk surface that is not merely minimal on a chosen spatial slice, but **extremal in the full Lorentzian spacetime**.

At leading order in classical Einstein gravity,

$$
S_A
=
\frac{\operatorname{Area}(X_A)}{4G_N},
$$

where $X_A$ is a codimension-two spacelike extremal surface in the bulk, anchored on $\partial A$ and homologous to $A$.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A boundary domain of dependence and a covariant HRT surface in a time-dependent AdS spacetime.](/figures/course/covariant-hrt-formula.svg)

<figcaption>

The HRT prescription replaces a minimal surface on a static time slice by a codimension-two extremal surface $X_A$ in the full Lorentzian bulk. The surface is anchored on $\partial A$, homologous to $A$, and obeys the two vanishing-expansion conditions $\theta_+=\theta_-=0$.

</figcaption>
</figure>

## Why RT needs a covariant upgrade

The RT formula taught us the first great lesson of holographic entanglement: an entropy in the boundary theory can be computed by a geometric area in the bulk. But the static formula has a built-in limitation. It asks for a minimal surface on a spatial slice, and that phrase only makes invariant sense when the spacetime has a suitable time symmetry.

In a time-dependent spacetime, different bulk slices can give different answers. A surface that is minimal on one slice may not be minimal, or even physically meaningful, on another. If the boundary state is undergoing collapse, or if a black hole is settling down, the bulk geometry knows about causal structure as well as spatial geometry. The entropy formula must therefore be Lorentzian.

The replacement is

$$
\text{RT: minimize area on a static slice}
\quad\longrightarrow\quad
\text{HRT: extremize area in Lorentzian spacetime}.
$$

This is a small verbal change but a major conceptual upgrade. It is the entry point to entanglement wedges, maximin methods, and the modern quantum-extremal-surface prescription.

## Boundary setup

Let the boundary theory live on a globally hyperbolic spacetime with a boundary Cauchy slice $\Sigma_{\partial}$. Choose a spatial region

$$
A\subset \Sigma_{\partial}.
$$

The reduced density matrix is $\rho_A$, obtained by tracing over the complement of $A$ on the same slice. In relativistic QFT, it is often better to associate the algebra of the region not just with $A$ itself, but with its **domain of dependence** $D[A]$.

The domain of dependence $D[A]$ is the set of boundary points whose physics is determined by initial data on $A$. Two regions with the same domain of dependence define the same causal subregion of the boundary theory. Therefore the geometric dual should depend on $D[A]$, not on an arbitrary choice of how one extends a boundary time slice into the bulk.

The entangling surface is

$$
\partial A.
$$

For a $d$-dimensional boundary theory, $\partial A$ has dimension $d-2$. The corresponding HRT surface $X_A$ is codimension two in the $(d+1)$-dimensional bulk, so it has dimension $d-1$.

## The HRT prescription

The classical HRT prescription is:

1. Find smooth spacelike codimension-two bulk surfaces $X$ such that

   $$
   \partial X = \partial A.
   $$

2. Impose the homology condition. There must exist a bulk achronal codimension-one region $R_A$ satisfying

   $$
   \partial R_A = A\cup X.
   $$

3. Require $X$ to be extremal:

   $$
   \delta \operatorname{Area}(X)=0
   $$

   under all local deformations preserving the boundary anchor.

4. If more than one admissible extremal surface exists, select the dominant one. In classical examples this is the smallest-area extremal surface among the allowed saddles. A more invariant way to organize the selection is the maximin construction discussed below.

Then

$$
S_A
=
\frac{\operatorname{Area}(X_A)}{4G_N}
+
\text{quantum corrections}.
$$

On this page we focus on the leading classical term. Bulk-entanglement corrections and quantum extremal surfaces are discussed later in the course.

## What “extremal” means

Let $X$ be a codimension-two spacelike surface in a Lorentzian bulk spacetime. Let $h_{ab}$ be the induced metric on $X$. Its area is

$$
\operatorname{Area}(X)
=
\int_X d^{d-1}\sigma\,\sqrt{h}.
$$

A small deformation of $X$ in a normal direction $s^a$ changes the area by

$$
\delta_s\operatorname{Area}(X)
=
-\int_X d^{d-1}\sigma\,\sqrt{h}\,K_a s^a
+
\text{boundary term}.
$$

If the anchor $\partial X=\partial A$ is held fixed, the boundary term vanishes. Therefore extremality means

$$
K^a=0,
$$

where $K^a$ is the mean-curvature vector of $X$.

Equivalently, choose two future-directed null normals $k^a$ and $\ell^a$ to $X$. The corresponding null expansions are

$$
\theta_{(k)}=h^{ab}\nabla_a k_b,
\qquad
\theta_{(\ell)}=h^{ab}\nabla_a \ell_b.
$$

The HRT condition is

$$
\theta_{(k)}=0,
\qquad
\theta_{(\ell)}=0.
$$

This is why the phrase “extremal surface” is better than “minimal surface.” In Lorentzian signature, the area is not minimized in every normal direction.

## How HRT reduces to RT

Suppose the bulk geometry is static and invariant under a time reflection $t\to -t$. Suppose also that the boundary region $A$ lies on the fixed slice $t=0$.

By symmetry, the HRT surface may be chosen to lie on the same time-reflection-symmetric slice. Deformations in the time direction vanish by symmetry. The remaining variational problem is minimization within the spatial slice. Therefore

$$
X_A=\gamma_A
\qquad
\text{in static time-symmetric settings},
$$

where $\gamma_A$ is the usual RT minimal surface.

RT is not a competing formula. It is the static limit of HRT.

## Homology and saddle selection

The anchor condition $\partial X=\partial A$ is not enough. The surface must also be homologous to $A$. This means there is a bulk region $R_A$ such that

$$
\partial R_A=A\cup X_A.
$$

The homology condition tells the surface which side it computes. It also distinguishes $A$ from its complement $\bar A$ in mixed states. For example, in a black-hole geometry, a surface homologous to a large boundary region may differ from a surface homologous to the complement by a horizon component.

Homology is also responsible for phase transitions. For disconnected boundary regions, different topologies of extremal surfaces can compete. The leading large-$N$ entropy chooses the dominant admissible saddle, and the answer can jump as one varies region sizes or time.

A useful slogan is

$$
\text{anchor tells the surface where to end; homology tells it which side it computes.}
$$

## The maximin picture

The maximin construction is a powerful way to think about HRT surfaces.

Start with a bulk Cauchy slice $\Sigma$ whose asymptotic boundary contains the boundary slice on which $A$ is defined. On $\Sigma$, find the minimal-area surface homologous to $A$:

$$
m_\Sigma(A)
=
\operatorname*{argmin}_{X\subset\Sigma,\,X\sim A}
\operatorname{Area}(X).
$$

Now vary $\Sigma$ and choose the slice-minimal surface whose area is maximal:

$$
X_A
=
\operatorname*{argmax}_{\Sigma}
\operatorname{Area}\!\left(m_\Sigma(A)\right).
$$

Thus the name is literal:

$$
\text{minimize on each slice, then maximize over slices.}
$$

Under suitable assumptions, the maximin surface agrees with the HRT surface. This viewpoint is especially useful for proving entropy inequalities, because it lets one recover some of the cut-and-paste intuition of RT surfaces even in covariant spacetimes.

## Causality constraints

The HRT formula must be compatible with boundary causality. The entropy of $A$ is an observable of the boundary domain $D[A]$. A change in the boundary state in a region causally disconnected from $D[A]$ should not instantly change $S_A$.

This imposes nontrivial constraints on the allowed bulk surface. In well-behaved classical geometries obeying suitable energy conditions, the HRT surface is causally protected: it is not casually accessible from $D[A]$ in a way that would violate the boundary domain-of-dependence property.

This statement is one of the reasons the covariant prescription is much more than “pick any extremal surface.” The correct surface must be extremal, homologous, and compatible with the causal structure of the boundary theory.

## Example: a boosted interval in AdS$_3$

In the vacuum of a two-dimensional holographic CFT, the bulk dual is pure AdS$_3$. For a spacelike interval with endpoint separation

$$
\Delta x^2-\Delta t^2>0,
$$

the HRT surface is the spacelike geodesic connecting the two endpoints. If the endpoints lie at equal boundary time, this is the familiar RT geodesic. If the endpoints are not simultaneous, a boundary Lorentz transformation maps the problem to the equal-time case.

The entropy is

$$
S_A
=
\frac{c}{3}\log\frac{\sqrt{\Delta x^2-\Delta t^2}}{\epsilon},
$$

where $\epsilon$ is the UV cutoff. This example is simple because symmetry does most of the work. In a genuinely time-dependent bulk, no symmetry may exist, and one must solve the Lorentzian extremal-surface problem directly.

## Example: collapse and entanglement growth

Consider a CFT state formed by injecting energy. The bulk may be modeled by a shell collapsing toward a black hole. At early boundary times, the HRT surface anchored on a region $A$ can mostly probe the pre-collapse geometry. At later times, the surface may cross the shell or probe the black-hole region.

This gives a geometric picture of entanglement growth after a quench:

$$
\text{time-dependent boundary entanglement}
\quad\longleftrightarrow\quad
\text{Lorentzian extremal surfaces in the bulk}.
$$

Larger regions generally have deeper HRT surfaces and can be sensitive to more of the evolving bulk. But the precise behavior depends on the state, the dimension, the shape of $A$, and the bulk matter content.

## Entropy inequalities

Entanglement entropy in quantum theory satisfies strong subadditivity:

$$
S_A+S_B
\ge
S_{A\cup B}+S_{A\cap B}.
$$

For static RT surfaces, strong subadditivity has a beautiful proof by cutting and regluing minimal surfaces on a common spatial slice. For HRT surfaces, the proof is subtler because the relevant extremal surfaces may not lie on the same bulk slice.

The maximin construction supplies the missing common-slice technology under suitable assumptions. This is one reason maximin is not just a technical device: it explains why the covariant entropy formula remains compatible with basic quantum-information inequalities.

A related property is **entanglement wedge nesting**. If boundary regions satisfy $A\subseteq B$, then the corresponding bulk entanglement wedges should satisfy

$$
\mathcal E[A]\subseteq \mathcal E[B].
$$

This nesting property is the main subject of the next page.

## Quantum corrections: a preview

The HRT formula is classical. At the next order, the entropy is not only area. Bulk quantum fields can themselves be entangled across the surface. The quantum-corrected formula is schematically

$$
S_A
=
\operatorname*{ext}_{X\sim A}
\left[
\frac{\operatorname{Area}(X)}{4G_N}
+
S_{\mathrm{bulk}}(R_X)
\right],
$$

where $R_X$ is the bulk region between $A$ and $X$. The extremizing surface is then called a quantum extremal surface.

This formula is not the main subject of the present page, but it is important to know why HRT is not the final word. HRT is the leading classical term in a more complete semiclassical expansion.

## Dictionary checkpoint

The HRT page upgrades the entanglement dictionary from static to covariant form:

| Boundary quantity | Bulk dual |
|---|---|
| region $A$ on a boundary Cauchy slice | boundary domain of dependence $D[A]$ |
| entangling surface $\partial A$ | anchor of the bulk surface |
| entropy $S_A$ at leading large $N$ | $\operatorname{Area}(X_A)/(4G_N)$ |
| static RT surface | minimal surface on a time-symmetric bulk slice |
| time-dependent entropy | Lorentzian extremal surface $X_A$ |
| homology condition | choice of the bulk side associated with $A$ |
| quantum corrections | bulk entanglement plus quantum extremization |

The slogan is

$$
\boxed{
S_A
=
\frac{\text{area of the covariant extremal surface anchored on }\partial A}{4G_N}
}
$$

at leading order in classical gravity.

## Common confusions

### “HRT surfaces are minimal surfaces in spacetime.”

Not quite. In Lorentzian signature the area functional is extremized, not minimized in all directions. On a chosen spacelike slice one can talk about minimization, but that slice is not generally canonical.

### “The HRT surface must lie at the same boundary time as $A$.”

No. In static examples it often does. In genuinely time-dependent geometries, the surface can bend through Lorentzian time while remaining anchored on $\partial A$.

### “Any extremal surface with the right endpoint works.”

No. One must impose homology and choose the correct dominant surface. Extremality alone is not enough.

### “The HRT formula gives the full reduced density matrix.”

No. It gives the leading large-$N$ entropy $S_A$. The richer question of which bulk region is encoded in $\rho_A$ leads to the entanglement wedge.

### “HRT is independent of the bulk equations of motion.”

No. The formula is used in a bulk geometry that solves the appropriate gravitational equations. Conversely, variations of holographic entanglement can be used to derive gravitational equations in suitable settings.

## Exercises

### Exercise 1: Extremal versus minimal

Explain why “minimal surface” is not the correct covariant replacement for RT in Lorentzian signature.

<details>
<summary><strong>Solution</strong></summary>

A codimension-two surface in Lorentzian spacetime has both spacelike and timelike normal directions. Deforming the surface in different normal directions can change the area with different signs. There is generally no invariant statement that the surface is a minimum in all normal directions. The invariant variational condition is instead

$$
\delta\operatorname{Area}(X)=0,
$$

or equivalently

$$
K^a=0.
$$

On a special time-symmetric spatial slice this extremal condition reduces to a spatial minimization problem, which is why RT is recovered in static settings.

</details>

### Exercise 2: Null expansions and extremality

Let $X$ be a codimension-two spacelike surface with future-directed null normals $k^a$ and $\ell^a$. Why does the HRT condition imply $\theta_{(k)}=\theta_{(\ell)}=0$?

<details>
<summary><strong>Solution</strong></summary>

The first variation of the area under a normal deformation is controlled by the mean-curvature vector $K^a$. The two independent normal directions can be chosen to be the null directions $k^a$ and $\ell^a$. The expansion $\theta_{(k)}$ measures the infinitesimal fractional change of the area element when the surface is deformed along $k^a$, and similarly for $\theta_{(\ell)}$.

If the surface is extremal under all normal deformations, the first-order change of area must vanish in both independent null directions. Thus

$$
\theta_{(k)}=0,
\qquad
\theta_{(\ell)}=0.
$$

Conversely, if both independent null expansions vanish, the mean-curvature vector vanishes, so the surface is extremal.

</details>

### Exercise 3: Recovering RT from HRT

Assume a static bulk geometry with a time-reflection symmetry $t\to -t$. Let $A$ lie on the fixed slice $t=0$. Explain why the HRT surface reduces to an RT surface on that slice.

<details>
<summary><strong>Solution</strong></summary>

The time-reflection symmetry maps any admissible surface anchored on $\partial A$ to another admissible surface with the same area. A symmetric extremal surface can therefore lie on the fixed slice $t=0$. Deformations normal to the slice are odd under the time reflection, so the first variation in the time direction vanishes by symmetry. The remaining variational problem is the minimization of area within the spatial slice. Hence the covariant HRT surface reduces to the RT minimal surface.

</details>

### Exercise 4: Why homology matters in a black-hole background

In a thermal state dual to an AdS black hole, explain why the homology condition can force horizon components to appear in entropy calculations for sufficiently large regions.

<details>
<summary><strong>Solution</strong></summary>

The homology condition requires a bulk region $R_A$ whose boundary is $A\cup X_A$. In a geometry with a horizon, a candidate surface with the correct anchor may fail to enclose the correct bulk region unless a horizon component is included. This is especially important when comparing the entropy of $A$ and the entropy of its complement $\bar A$ in a mixed thermal state. The possible inclusion of the horizon is what allows the holographic entropy to reproduce thermal entropy contributions.

</details>

## Further reading

- V. E. Hubeny, M. Rangamani, and T. Takayanagi, [A Covariant Holographic Entanglement Entropy Proposal](https://arxiv.org/abs/0705.0016).
- A. C. Wall, [Maximin Surfaces, and the Strong Subadditivity of the Covariant Holographic Entanglement Entropy](https://arxiv.org/abs/1211.3494).
- M. Headrick, V. E. Hubeny, A. Lawrence, and M. Rangamani, [Causality & Holographic Entanglement Entropy](https://arxiv.org/abs/1408.6300).
- A. Lewkowycz and J. Maldacena, [Generalized Gravitational Entropy](https://arxiv.org/abs/1304.4926).
- X. Dong, A. Lewkowycz, and M. Rangamani, [Deriving Covariant Holographic Entanglement](https://arxiv.org/abs/1607.07506).
