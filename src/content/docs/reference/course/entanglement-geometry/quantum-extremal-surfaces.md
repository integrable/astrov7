---
title: "Quantum Extremal Surfaces"
description: "The quantum-corrected holographic entropy formula, generalized entropy, FLM corrections, and quantum entanglement wedges."
sidebar:
  order: 60
---

The RT and HRT formulas are classical gravitational formulas. They compute the leading large-$N$ contribution to boundary entanglement entropy:

$$
S_A
=
\frac{\operatorname{Area}(X_A)}{4G_N}
+O(N^0).
$$

But the bulk is not exactly classical. Even when the geometry is weakly curved, there are quantum fields in the bulk, and those fields can be entangled across the surface $X_A$. The classical area term is therefore only the first term in a quantum expansion.

The correct object is the **generalized entropy**:

$$
S_{\mathrm{gen}}(X)
=
\frac{\operatorname{Area}(X)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_X)
+\text{local counterterms}.
$$

A **quantum extremal surface** is a surface that extremizes $S_{\mathrm{gen}}$, not just area. The quantum-corrected holographic entropy is

$$
\boxed{
S_A
=
\min_X\,\operatorname*{ext}_X
\left[
\frac{\operatorname{Area}(X)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_X)
+\cdots
\right].
}
$$

This formula is the quantum successor of RT/HRT.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A quantum extremal surface displaced from a classical HRT surface by bulk entanglement across the wedge.](/figures/course/quantum-extremal-surfaces.svg)

<figcaption>

A classical HRT surface extremizes area. A quantum extremal surface extremizes generalized entropy $S_{\mathrm{gen}}=\operatorname{Area}/(4G_N)+S_{\mathrm{bulk}}+\cdots$. The surface can shift because bulk quantum fields are entangled across the candidate entanglement wedge $\Sigma_X$.

</figcaption>
</figure>

## Why quantum extremal surfaces are needed

Classical RT/HRT is the leading saddle in the bulk semiclassical expansion. In standard large-$N$ gauge theory examples,

$$
\frac{\operatorname{Area}}{4G_N}
\sim
N^2.
$$

But the boundary entropy also has subleading pieces of order $N^0$, $1/N^2$, and so on. These corrections come from bulk quantum fields, graviton loops, stringy corrections, and higher-derivative terms in the effective gravitational action.

The most universal correction is bulk entanglement. If the boundary region $A$ is dual to a bulk region $a$, then bulk fields inside $a$ can be entangled with bulk fields outside $a$. This entropy contributes to the entropy of $\rho_A$.

Thus the classical formula

$$
S_A=\frac{\operatorname{Area}(X_A)}{4G_N}
$$

must be replaced by a formula that counts both geometry and bulk quantum information.

## The FLM correction

At the first subleading order around a classical RT/HRT surface $X_A^{(0)}$, the Faulkner–Lewkowycz–Maldacena correction gives

$$
S_A
=
\frac{\operatorname{Area}(X_A^{(0)})}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_{X_A^{(0)}})
+O(G_N).
$$

Here $\Sigma_{X_A^{(0)}}$ is the classical homology region satisfying

$$
\partial\Sigma_{X_A^{(0)}}=A\cup X_A^{(0)}.
$$

The term $S_{\mathrm{bulk}}$ is the ordinary von Neumann entropy of the bulk effective field theory in that region. This is not a decorative correction. It is required by the fact that the bulk itself is a quantum system.

Why can we evaluate the bulk entropy on the classical surface at this order? Because the classical surface is already extremal. If the true quantum surface shifts by an amount of order $G_N$, the corresponding change in the area term begins only at the next order. Therefore the first $O(N^0)$ correction is simply the bulk entropy across the classical surface.

## Generalized entropy

For a candidate codimension-two surface $X$ anchored on $\partial A$ and homologous to $A$, choose a bulk region $\Sigma_X$ such that

$$
\partial\Sigma_X=A\cup X.
$$

The generalized entropy is

$$
S_{\mathrm{gen}}(X)
=
\frac{\operatorname{Area}(X)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_X)
+S_{\mathrm{local}}(X).
$$

The local term $S_{\mathrm{local}}(X)$ is important. Bulk entanglement entropy is ultraviolet divergent. Its divergences are local geometric functionals of the surface and are absorbed into the renormalization of Newton's constant and higher-derivative gravitational couplings.

Thus the finite object is not “bare area plus finite bulk entropy.” It is a renormalized combination:

$$
S_{\mathrm{gen}}^{\mathrm{ren}}
=
S_{\mathrm{grav}}^{\mathrm{ren}}+S_{\mathrm{bulk}}^{\mathrm{ren}}.
$$

For Einstein gravity at leading order, the gravitational part is simply $\operatorname{Area}/(4G_N)$. In higher-derivative gravity, the area term is replaced by an appropriate gravitational entropy functional, such as the Wald–Dong functional, plus quantum corrections.

## The QES condition

A quantum extremal surface $X_A$ satisfies

$$
\delta_X S_{\mathrm{gen}}(X_A)=0.
$$

Equivalently, deformations in either independent normal direction leave the generalized entropy stationary:

$$
\frac{\delta S_{\mathrm{gen}}}{\delta X^a}=0.
$$

For Einstein gravity plus bulk quantum fields, this condition has the schematic form

$$
\frac{1}{4G_N}K_a
+
\frac{\delta S_{\mathrm{bulk}}}{\delta X^a}
+\cdots
=0,
$$

where $K_a$ is the trace of the extrinsic curvature vector of $X$.

Classically, $S_{\mathrm{bulk}}$ is absent and the condition reduces to

$$
K_a=0,
$$

which is the HRT extremality condition. Quantum mechanically, the surface is pushed by the shape dependence of bulk entanglement.

After finding all relevant quantum extremal surfaces, one chooses the one with smallest generalized entropy:

$$
S_A=\min_{X_A}S_{\mathrm{gen}}(X_A).
$$

So the rule is: **extremize first, then minimize**.

## Perturbative displacement of the surface

Let $y$ be a small normal displacement away from a classical HRT surface. Suppose

$$
\frac{\operatorname{Area}(y)}{4G_N}
=
\frac{\operatorname{Area}(0)}{4G_N}
+
\frac{a}{8G_N}y^2+O(y^3),
$$

and

$$
S_{\mathrm{bulk}}(y)=S_0+s_1y+O(y^2).
$$

Then

$$
S_{\mathrm{gen}}(y)
=
\frac{\operatorname{Area}(0)}{4G_N}
+
\frac{a}{8G_N}y^2
+S_0+s_1y+\cdots.
$$

The QES condition gives

$$
0=\frac{dS_{\mathrm{gen}}}{dy}
=\frac{a}{4G_N}y+s_1+\cdots,
$$

so

$$
y_\ast=-\frac{4G_Ns_1}{a}+O(G_N^2).
$$

Thus the QES is usually displaced from the classical surface by order $G_N$. However, near a phase transition between competing surfaces, an order-$N^0$ bulk entropy term can change which surface dominates. This is why quantum effects can be qualitatively important even when the semiclassical expansion is good.

## Quantum entanglement wedges

Once the surface becomes quantum-corrected, the entanglement wedge must also be updated.

Let $X_A^{\mathrm{QES}}$ be the selected quantum extremal surface. Let $\Sigma_A^{\mathrm{QES}}$ be a bulk region satisfying

$$
\partial\Sigma_A^{\mathrm{QES}}
=A\cup X_A^{\mathrm{QES}}.
$$

The **quantum entanglement wedge** is the bulk domain of dependence of this region:

$$
\mathcal E_Q[A]
=
D_{\mathrm{bulk}}[\Sigma_A^{\mathrm{QES}}].
$$

The subregion dictionary becomes

$$
\boxed{
\rho_A
\quad\longleftrightarrow\quad
\mathcal E_Q[A].
}
$$

At leading order, $\mathcal E_Q[A]$ reduces to the classical entanglement wedge. At subleading order, the surface and wedge can shift. In black-hole settings, the shift can be dramatic because a different QES topology can dominate.

## Relation to JLMS and the first law

The JLMS relation says, schematically, that within a semiclassical code subspace,

$$
K_A^{\mathrm{CFT}}
=
\frac{\widehat{\operatorname{Area}}(X_A)}{4G_N}
+K_{\Sigma_A}^{\mathrm{bulk}}
+\cdots.
$$

Taking variations gives

$$
\delta S_A
=
\delta\left\langle\frac{\widehat{\operatorname{Area}}(X_A)}{4G_N}\right\rangle
+
\delta S_{\mathrm{bulk}}(\Sigma_A)
+
\cdots.
$$

This is the variation of generalized entropy:

$$
\delta S_A=\delta S_{\mathrm{gen}}.
$$

Thus QES is not an arbitrary embellishment of RT. It is what the modular Hamiltonian and bulk relative-entropy dictionary require once bulk quantum fields are included.

## Islands as a preview

Quantum extremal surfaces are the mechanism behind entanglement islands. In island problems, the region $\Sigma_X$ homologous to a boundary or radiation region can include a disconnected gravitational region. The entropy is still computed by extremizing generalized entropy.

A schematic island formula is

$$
S(R)
=
\min_I\,\operatorname*{ext}_{\partial I}
\left[
\frac{\operatorname{Area}(\partial I)}{4G_N}
+S_{\mathrm{bulk}}(R\cup I)
\right].
$$

This is not a different principle. It is the QES prescription applied to a setup involving a gravitating region and a nongravitating radiation region. The next page will treat islands and black-hole information more carefully.

## Dictionary checkpoint

| Classical entanglement dictionary | Quantum-corrected dictionary |
|---|---|
| RT/HRT surface | quantum extremal surface |
| area functional | generalized entropy |
| $S_A=\operatorname{Area}/(4G_N)$ | $S_A=\min\operatorname*{ext}S_{\mathrm{gen}}$ |
| classical entanglement wedge | quantum entanglement wedge |
| classical extremality $K_a=0$ | quantum extremality $\delta S_{\mathrm{gen}}=0$ |
| leading large-$N$ entropy | entropy including bulk quantum corrections |

The essential formula is

$$
\boxed{
S_{\mathrm{gen}}(X)
=
\frac{\operatorname{Area}(X)}{4G_N}
+S_{\mathrm{bulk}}(\Sigma_X)
+\cdots.
}
$$

## Common confusions

### “QES is just the RT surface plus a tiny shift.”

Often it is perturbatively close to the RT/HRT surface. But when multiple candidate surfaces compete, an order-$N^0$ bulk entropy term can change which surface wins. This is the mechanism behind many quantum phase transitions of entanglement wedges.

### “Bulk entropy is separately finite.”

No. Bulk entanglement entropy is UV divergent. The finite physical object is the renormalized generalized entropy as a whole.

### “Extremize means minimize.”

No. First find surfaces that extremize $S_{\mathrm{gen}}$. Then choose the one with smallest generalized entropy among the allowed extrema.

### “QES is only about islands.”

No. QES is the general quantum correction to holographic entanglement entropy. Islands are one dramatic application.

## Exercises

### Exercise 1: Classical limit

Show that the QES condition reduces to the HRT condition when $G_N\to0$ and $S_{\mathrm{bulk}}$ remains order $G_N^0$.

<details>
<summary><strong>Solution</strong></summary>

The QES condition is

$$
0=\delta S_{\mathrm{gen}}
=\frac{1}{4G_N}\delta\operatorname{Area}
+\delta S_{\mathrm{bulk}}+
\cdots.
$$

Multiplying by $4G_N$ gives

$$
0=\delta\operatorname{Area}+4G_N\delta S_{\mathrm{bulk}}+
\cdots.
$$

If $\delta S_{\mathrm{bulk}}$ is finite as $G_N\to0$, the second term vanishes, leaving

$$
\delta\operatorname{Area}=0.
$$

This is the HRT extremality condition.

</details>

### Exercise 2: QES displacement

Using

$$
S_{\mathrm{gen}}(y)
=
\frac{A_0}{4G_N}
+
\frac{a}{8G_N}y^2
+S_0+s_1y+
O(y^2),
$$

find the leading displacement $y_\ast$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dS_{\mathrm{gen}}}{dy}
=
\frac{a}{4G_N}y+s_1+
\cdots.
$$

Setting this to zero gives

$$
y_\ast=-\frac{4G_Ns_1}{a}+O(G_N^2).
$$

</details>

### Exercise 3: Why FLM evaluates bulk entropy on the classical surface

Explain why the shift of the surface does not affect the entropy at order $G_N^0$.

<details>
<summary><strong>Solution</strong></summary>

The displacement is $y_\ast=O(G_N)$. The area functional has no linear term around the classical extremal surface, so the area change from the displacement is quadratic:

$$
\Delta\left(\frac{A}{4G_N}\right)
\sim
\frac{1}{G_N}y_\ast^2
\sim
G_N.
$$

The bulk entropy changes by

$$
\Delta S_{\mathrm{bulk}}
\sim y_\ast
\sim G_N.
$$

Therefore, through order $G_N^0$, one evaluates $S_{\mathrm{bulk}}$ on the classical surface. This is the FLM formula.

</details>

### Exercise 4: Renormalized generalized entropy

Why is it misleading to say that generalized entropy is “area plus finite bulk entropy”?

<details>
<summary><strong>Solution</strong></summary>

Bulk entanglement entropy across a surface is UV divergent. Its divergences are local on the surface and are absorbed into the renormalization of $G_N$ and higher-curvature couplings. The split into geometric and bulk terms can be scheme-dependent. The finite physical quantity is the renormalized generalized entropy as a whole.

</details>

## Further reading

- T. Faulkner, A. Lewkowycz, and J. Maldacena, [Quantum corrections to holographic entanglement entropy](https://arxiv.org/abs/1307.2892).
- N. Engelhardt and A. C. Wall, [Quantum Extremal Surfaces: Holographic Entanglement Entropy beyond the Classical Regime](https://arxiv.org/abs/1408.3203).
- D. L. Jafferis, A. Lewkowycz, J. Maldacena, and S. J. Suh, [Relative entropy equals bulk relative entropy](https://arxiv.org/abs/1512.06431).
- X. Dong, [Holographic Entanglement Entropy for General Higher Derivative Gravity](https://arxiv.org/abs/1310.5713).
- A. C. Wall, [A proof of the generalized second law for rapidly changing fields and arbitrary horizon slices](https://arxiv.org/abs/1105.3445).
