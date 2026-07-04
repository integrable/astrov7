---
title: "Why Renormalization Is Needed"
description: "Why AdS on-shell actions diverge, how the UV/IR relation turns bulk infrared divergences into boundary ultraviolet divergences, and why local counterterms are part of the holographic dictionary."
sidebar:
  order: 10
---

The previous unit stated the dictionary in its most useful form:

$$
Z_{\rm CFT}[\text{sources}]
=
Z_{\rm bulk}[\text{asymptotic boundary data}]
\,.
$$

In the classical saddle approximation this becomes

$$
W_{\rm CFT}[\text{sources}]
=
\log Z_{\rm CFT}[\text{sources}]
\simeq
-S_{\text{on-shell}}[\text{boundary data}]\,.
$$

That formula is not yet a well-defined computational prescription. The raw bulk on-shell action diverges. The boundary value of a field at $z=0$ is usually infinite or zero in the naive coordinate normalization. The Brown–York stress tensor diverges. Even pure AdS has infinite volume. If one differentiates the unrenormalized on-shell action, one typically obtains cutoff-dependent answers rather than CFT correlation functions.

Holographic renormalization is the procedure that fixes this. It is the bulk version of ordinary QFT renormalization: introduce a cutoff, identify local divergences, add local counterterms, remove the cutoff, and define finite renormalized observables.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A cutoff surface near the AdS boundary regulates the infinite-volume region. Divergences live locally on the cutoff surface and are cancelled by counterterms before the cutoff is removed.](/figures/course/holographic-renormalization-uv-ir.svg)

<figcaption>

Holographic renormalization. A cutoff surface $z=\epsilon$ regulates the asymptotic AdS region. The same cutoff is interpreted in the boundary theory as a UV regulator $\approx 1/\epsilon$. Local counterterms on the cutoff surface cancel divergences of the on-shell action and define finite one-point functions.

</figcaption>
</figure>

## Why this matters

The dictionary is often written as if one could simply plug the classical solution into the bulk action and differentiate. This is a good mnemonic, but not a complete prescription. The complete classical relation is instead

$$
W_{\rm CFT}[J]
\simeq
-S_{\text{ren,on-shell}}[J] \, ,
$$

where $S_{\text{ren,on-shell}}$ is not the original action. It is the regulated on-shell action plus boundary counterterms, with the regulator removed.

This distinction is not pedantic. It controls several things that students otherwise find mysterious:

1. **Finite correlation functions.** The raw on-shell action contains powers of the cutoff and sometimes logarithms of the cutoff.
2. **Correct one-point functions.** The vev is a renormalized canonical momentum, not merely the first coefficient that looks subleading.
3. **Ward identities.** Conservation laws and trace anomalies emerge cleanly only after the correct counterterms are included.
4. **Scheme dependence.** Finite local counterterms change contact terms and local pieces of one-point functions, just as in ordinary QFT.
5. **The Weyl anomaly.** In even boundary dimensions, logarithmic divergences become conformal anomalies.

The slogan is:

$$
\boxed{
\text{bulk infrared divergence near }z=0
\quad\leftrightarrow\quad
\text{boundary ultraviolet divergence}
}
$$

This is the UV/IR relation in one of its sharpest operational forms.

## The simplest divergence: the volume of AdS

Use Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+d\vec x^{\,2}\right),
\qquad z>0.
$$

The conformal boundary is at $z=0$. The bulk volume element is

$$
\sqrt{G}
=
\frac{L^{d+1}}{z^{d+1}}\,.
$$

Regulate the geometry by cutting it off at

$$
z=\epsilon\,.
$$

The volume per unit boundary volume is then

$$
\frac{\mathrm{Vol}}{\mathrm{Vol}(\mathbb R^d)}
=
\int_\epsilon^\infty dz\,\frac{L^{d+1}}{z^{d+1}}
=
\frac{L^{d+1}}{d\,\epsilon^d}\,.
$$

Thus even empty AdS has an infinite regulated volume as $\epsilon\to0$. Since the gravitational action contains a bulk integral, the on-shell action diverges before any matter fields are turned on.

This divergence is not a pathology of AdS/CFT. It is the gravitational representation of the ultraviolet divergences of a QFT placed on an infinite hierarchy of short-distance scales.

## The UV/IR relation

Poincaré AdS has the scaling symmetry

$$
z\to \lambda z,
\qquad
x^i\to \lambda x^i.
$$

The radial coordinate $z$ scales like a boundary length. Therefore a cutoff $z=\epsilon$ corresponds to a short-distance cutoff in the boundary theory:

$$
\ell_{\rm UV}\sim \epsilon,
\qquad
\Lambda_{\rm UV}\sim \frac{1}{\epsilon}\,.
$$

Near the boundary, small $z$ means high boundary energy. Deep in the bulk, large $z$ means low boundary energy. This is the sense in which the AdS radial direction geometrizes renormalization scale.

One should not take the relation $\Lambda_{\rm UV}\sim1/\epsilon$ too literally beyond leading scaling. The precise numerical conversion is scheme-dependent and depends on the choice of conformal frame and defining function. The robust statement is that approaching the AdS boundary probes shorter and shorter boundary distances.

## Regulating the bulk problem

The classical bulk action is first evaluated on the region

$$
M_\epsilon=\{z\ge \epsilon\}\,.
$$

The cutoff surface $\Sigma_\epsilon$ has induced metric

$$
\gamma_{ij}(\epsilon,x)
=
\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x)
$$

in Fefferman–Graham coordinates,

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{ij}(z,x)dx^i dx^j\right).
$$

The regulated action has the schematic form

$$
S_{\rm reg}(\epsilon)
=
S_{\rm bulk}^{z\ge\epsilon}
+S_{\rm GHY}^{z=\epsilon}
+S_{\rm matter,bdy}^{z=\epsilon}
$$

where $S_{\rm GHY}$ is the Gibbons–Hawking–York term needed for a well-posed Dirichlet variational principle for the metric. For scalars or gauge fields, additional finite or divergent boundary terms may be needed depending on boundary conditions.

The renormalized action is defined by adding local counterterms on $\Sigma_\epsilon$:

$$
\boxed{
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left[
S_{\rm reg}(\epsilon)+S_{\rm ct}(\epsilon)
\right].
}
$$

The counterterms are local functionals of the induced fields at the cutoff surface:

$$
S_{\rm ct}(\epsilon)
=
\int_{z=\epsilon} d^d x\sqrt{|\gamma|}\,
\mathcal L_{\rm ct}
\left(\gamma_{ij},\Phi,A_i,\nabla_i,\ldots\right).
$$

Locality is the key. Divergences come from the asymptotic region and are determined by the near-boundary expansion. They cannot depend on global interior information such as whether the bulk ends smoothly, contains a horizon, or has a normalizable excitation.

## Scalar example: why the on-shell action diverges

Consider a scalar field in fixed Euclidean AdS$_{d+1}$:

$$
S_\phi
=
\frac12
\int d^{d+1}x\sqrt{G}
\left(G^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right).
$$

On shell, after integrating by parts, the action reduces to a boundary term,

$$
S_{\phi,{\rm os}}
=
\frac12
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,
\phi\,n^M\partial_M\phi
$$

up to a sign that depends on the orientation convention for the outward normal. The divergence structure is independent of this sign.

Near the boundary, the scalar behaves as

$$
\phi(z,x)
=
z^{d-\Delta}\left(\phi_{(0)}(x)+\cdots\right)
+
z^\Delta\left(A(x)+\cdots\right),
$$

where

$$
m^2L^2=\Delta(\Delta-d)\,.
$$

If the source $\phi_{(0)}$ is nonzero, the leading contribution to the on-shell action scales as

$$
S_{\phi,{\rm os}}
\sim
\epsilon^{d-2\Delta}
\int d^d x\,\phi_{(0)}^2+\cdots .
$$

For an operator with $\Delta>d/2$, this diverges as $\epsilon\to0$. Derivative terms in the expansion generate additional divergences involving

$$
\phi_{(0)}\Box\phi_{(0)},
\qquad
\phi_{(0)}\Box^2\phi_{(0)},
\qquad
\ldots
$$

all of which are local in the source. Holographic renormalization subtracts precisely these local divergent pieces.

The leading scalar counterterm has the schematic form

$$
S_{\phi,{\rm ct}}
\supset
\frac12
\int_{z=\epsilon}d^d x\sqrt{\gamma}\,
\frac{d-\Delta}{L}\,\phi^2,
$$

again with the overall sign determined by the action and normal conventions. Higher counterterms contain boundary derivatives, for example terms proportional to $\phi\Box_\gamma\phi$. The important point is that they are local functionals on the cutoff surface.

## Gravity example: counterterms for the metric

For pure Einstein gravity with negative cosmological constant, the regulated Dirichlet action is

$$
S_{\rm grav,reg}
=
\frac{1}{16\pi G_{d+1}}
\int_{M_\epsilon} d^{d+1}x\sqrt{|G|}\,(R-2\Lambda)
+
\frac{1}{8\pi G_{d+1}}
\int_{\Sigma_\epsilon}d^d x\sqrt{|\gamma|}\,K.
$$

The cosmological constant is

$$
\Lambda=-\frac{d(d-1)}{2L^2}\,.
$$

The first counterterms are of the form

$$
S_{\rm ct}
=
-\frac{1}{8\pi G_{d+1}}
\int_{\Sigma_\epsilon}d^d x\sqrt{|\gamma|}
\left[
\frac{d-1}{L}
+
\frac{L}{2(d-2)}R[\gamma]
+
\cdots
\right],
$$

for $d>2$, with additional terms and logarithmic counterterms in special dimensions. The leading term cancels the volume divergence. The curvature term cancels subleading divergences caused by putting the CFT on a curved background metric.

The renormalized stress tensor is then the counterterm-improved Brown–York tensor:

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta W_{\rm CFT}}{\delta g_{(0)ij}}
\simeq
-\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta S_{\rm ren}}{\delta g_{(0)ij}}
$$

in the Euclidean convention used in this course. The unrenormalized Brown–York tensor diverges; the renormalized one has a finite limit.

## Sources are not raw cutoff values

A subtle point is worth isolating. At $z=\epsilon$, the scalar field itself behaves as

$$
\phi(\epsilon,x)
\sim
\epsilon^{d-\Delta}\phi_{(0)}(x).
$$

Thus the source is not simply the raw cutoff value $\phi(\epsilon,x)$; it is the properly rescaled coefficient

$$
\phi_{(0)}(x)
=
\lim_{\epsilon\to0}\epsilon^{\Delta-d}\phi(\epsilon,x)
$$

in standard quantization. Similarly, the CFT metric source is not the induced metric $\gamma_{ij}$ itself, which diverges as $\epsilon^{-2}$, but the finite representative

$$
g_{(0)ij}(x)
=
\lim_{\epsilon\to0}\frac{\epsilon^2}{L^2}\gamma_{ij}(\epsilon,x).
$$

This is why holographic renormalization is not just “subtract infinity.” It also tells us which finite boundary data are held fixed while taking the cutoff away.

## What is universal and what is scheme-dependent?

The divergent counterterms are fixed by the requirement that the regulated variational problem and correlation functions become finite. Finite local counterterms may still be added:

$$
S_{\rm ren}
\to
S_{\rm ren}+S_{\rm finite,local}[g_{(0)},J,A_{(0)},\ldots] .
$$

These finite terms define a renormalization scheme. They can change contact terms, local pieces of one-point functions, and coefficients of terms that are not protected by Ward identities. They cannot change separated-point nonlocal correlators or physical quantities that are scheme-independent.

This exactly mirrors ordinary QFT. For example, adding a finite local term

$$
\int d^d x\sqrt{|g_{(0)}|}\,J^2
$$

changes the two-point function of the operator sourced by $J$ by a contact term proportional to $\delta^{(d)}(x-y)$.

## Logarithms and anomalies

In even boundary dimensions, holographic renormalization often produces logarithmic divergences:

$$
S_{\rm reg}+S_{\rm ct}
\supset
\log\epsilon
\int d^d x\sqrt{|g_{(0)}|}\,\mathcal A[g_{(0)},J,\ldots].
$$

The coefficient $\mathcal A$ is not an arbitrary nuisance. It is the holographic Weyl anomaly. Under a Weyl transformation of the boundary metric,

$$
g_{(0)ij}\to e^{2\sigma(x)}g_{(0)ij},
$$

the renormalized generating functional transforms anomalously:

$$
\delta_\sigma W_{\rm CFT}
=
\int d^d x\sqrt{|g_{(0)}|}\,\sigma(x)\mathcal A(x).
$$

Equivalently,

$$
\langle T^i_{\ i}\rangle=\mathcal A
$$

when all explicit source beta-function terms are absent. Thus the logarithmic divergence in the bulk knows about the trace anomaly of the boundary CFT.

## What near-boundary analysis can and cannot determine

The divergences of the on-shell action are determined locally by sources. That is why counterterms can be found from an asymptotic expansion near $z=0$.

But the state of the CFT is not determined by sources alone. To know the vev, one usually needs information from the interior:

- regularity in Euclidean AdS;
- incoming boundary conditions at a Lorentzian horizon;
- normalizability in global AdS;
- smoothness at the cap of a soliton geometry;
- a choice of black-hole saddle.

The near-boundary expansion has both locally determined coefficients and undetermined normalizable coefficients. The latter encode one-point functions and state data. The next page makes this precise.

## The basic algorithm

At the first working level, holographic renormalization proceeds as follows:

1. **Choose a cutoff.** Work on $M_\epsilon$ with boundary $\Sigma_\epsilon$ near the conformal boundary.
2. **Fix finite sources.** Identify the rescaled boundary data $g_{(0)ij}$, $J$, $A_{(0)i}$, and so on.
3. **Solve asymptotically.** Expand the bulk fields near $z=0$ and solve the equations recursively.
4. **Evaluate the regulated action.** Substitute the asymptotic solution into the on-shell action.
5. **Add local counterterms.** Cancel all divergent terms using local functionals of cutoff data.
6. **Take the limit.** Define $S_{\rm ren}$ by sending $\epsilon\to0$.
7. **Differentiate.** Obtain renormalized one-point functions and correlators by functional differentiation.

Schematically,

$$
\boxed{
\text{solve} \to \text{regulate} \to \text{subtract} \to \text{differentiate}
}
$$

This is the practical form of the GKP/Witten prescription.

## Dictionary checkpoint

The main translations from this page are:

| Boundary QFT | Bulk AdS |
|---|---|
| UV cutoff $\Lambda_{\rm UV}$ | radial cutoff $z=\epsilon\sim 1/\Lambda_{\rm UV}$ |
| source $J$ | rescaled leading asymptotic coefficient of a bulk field |
| UV divergence of $W[J]$ | near-boundary divergence of $S_{\text{on-shell}}$ |
| local QFT counterterm | local boundary term on $\Sigma_\epsilon$ |
| renormalized generating functional | renormalized on-shell action |
| conformal anomaly | logarithmic divergence of the bulk action |
| scheme dependence | finite local counterterms |

The most important formula is

$$
\boxed{
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left[
S_{\rm bulk}^{z\ge\epsilon}
+S_{\rm GHY}^{z=\epsilon}
+S_{\rm ct}^{z=\epsilon}
\right].
}
$$

## Common confusions

### “The bulk divergence means the duality is ill-defined.”

No. The divergence means that the raw gravitational action is a regulated object, just like the bare generating functional in QFT. The finite observable is obtained only after adding counterterms and removing the regulator.

### “Counterterms are arbitrary decorations.”

Divergent counterterms are fixed by finiteness and covariance. Finite local counterterms represent scheme choices. They are not arbitrary changes of the theory; they are the holographic version of choosing a renormalization scheme in QFT.

### “The cutoff surface is the physical boundary.”

No. The cutoff surface is a regulator. The CFT source is defined by an asymptotic coefficient that remains finite as the cutoff is removed. The physical conformal boundary is reached only after taking the limit.

### “The vev is always just the normalizable coefficient.”

Not quite. The normalizable coefficient carries the nonlocal state-dependent information, but the renormalized one-point function can also include local terms determined by sources and finite counterterms. The clean definition is always by variation of $S_{\rm ren}$.

### “Holographic renormalization only matters for curved boundaries.”

It matters even for flat boundaries and scalar correlators. Curved boundaries make the geometric structure more visible, but the need for counterterms already appears in the simplest scalar two-point calculation.

## Exercises

### Exercise 1: Pure AdS volume divergence

In Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2=\frac{L^2}{z^2}(dz^2+d\vec x^{\,2}),
$$

show that the regulated volume per unit boundary volume diverges as $\epsilon^{-d}$.

<details>
<summary><strong>Solution</strong></summary>

The determinant gives

$$
\sqrt{G}=\frac{L^{d+1}}{z^{d+1}}.
$$

Therefore

$$
\frac{\mathrm{Vol}}{\mathrm{Vol}(\mathbb R^d)}
=
\int_\epsilon^\infty dz\,\frac{L^{d+1}}{z^{d+1}}
=
\frac{L^{d+1}}{d\epsilon^d}.
$$

Thus the divergence is proportional to $\epsilon^{-d}$.

</details>

### Exercise 2: Leading scalar divergence

For a scalar with

$$
\phi(z,x)\sim z^{d-\Delta}\phi_{(0)}(x),
$$

estimate the leading cutoff dependence of the on-shell boundary term

$$
S_{\phi,{\rm os}}
\sim
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\phi\,n^z\partial_z\phi.
$$

<details>
<summary><strong>Solution</strong></summary>

On the cutoff surface,

$$
\sqrt{\gamma}\sim \epsilon^{-d},
\qquad
\phi\sim \epsilon^{d-\Delta}\phi_{(0)},
\qquad
n^z\partial_z\phi\sim \epsilon\partial_z\phi\sim (d-\Delta)\epsilon^{d-\Delta}\phi_{(0)},
$$

up to powers of $L$ and orientation signs. Therefore

$$
S_{\phi,{\rm os}}
\sim
\epsilon^{-d}\epsilon^{d-\Delta}\epsilon^{d-\Delta}
\int d^d x\,\phi_{(0)}^2
=
\epsilon^{d-2\Delta}\int d^d x\,\phi_{(0)}^2.
$$

For $\Delta>d/2$, this diverges as $\epsilon\to0$.

</details>

### Exercise 3: A finite local counterterm

Suppose one adds a finite counterterm

$$
S_{\rm finite}=c\int d^d x\,J(x)^2
$$

to the renormalized action for a scalar source $J$. What happens to the two-point function?

<details>
<summary><strong>Solution</strong></summary>

The one-point function changes by a local term proportional to $J$:

$$
\langle\mathcal O(x)\rangle\to
\langle\mathcal O(x)\rangle+2cJ(x)
$$

up to the sign convention relating $W$ and $S_{\rm ren}$. Differentiating once more with respect to $J(y)$ gives a contact-term shift

$$
\langle\mathcal O(x)\mathcal O(y)\rangle
\to
\langle\mathcal O(x)\mathcal O(y)\rangle
+2c\,\delta^{(d)}(x-y).
$$

Separated-point correlators are unchanged.

</details>

## Further reading

- Sebastian de Haro, Kostas Skenderis, and Sergey N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- Massimo Bianchi, Daniel Z. Freedman, and Kostas Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- Kostas Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- Mans Henningson and Kostas Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).
- Ioannis Papadimitriou and Kostas Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
