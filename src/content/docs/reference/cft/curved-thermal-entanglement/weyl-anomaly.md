---
title: "Weyl Anomaly"
description: "Trace anomalies, curved-space sources, scheme dependence, and the holographic origin of Weyl anomalies."
sidebar:
  order: 2
---

## Why Weyl anomalies matter

A CFT is locally insensitive to changes of scale. On flat space this is usually summarized by

$$
T^\mu{}_{\mu}=0,
$$

after possible improvement of the stress tensor. On a curved background this statement becomes subtler. The metric is not just geometry; it is the source for the stress tensor. Once the theory is regulated, the path-integral measure and the counterterms needed to define the generating functional may fail to be invariant under local Weyl transformations. The result is a **Weyl anomaly**, also called a **trace anomaly**.

The anomaly is one of the cleanest places where a CFT remembers both quantum mechanics and geometry:

$$
\boxed{
\text{classical Weyl invariance}
\quad\not\Rightarrow\quad
\text{quantum Weyl invariance on curved space}.
}
$$

This is not a small technical correction. In two dimensions, the coefficient of the Weyl anomaly is the central charge $c$. In four dimensions, the anomaly contains the central charges $a$ and $c$. In holography, the same anomaly is produced by logarithmic divergences of the bulk on-shell action. So the Weyl anomaly is simultaneously a CFT observable, a curved-space Ward identity, and a diagnostic of the bulk gravitational dynamics.

---

## Metric source and Weyl variation

We use the Euclidean convention introduced earlier:

$$
W[g,A,\lambda]=-\log \mathcal Z[g,A,\lambda].
$$

The one-point function of the stress tensor is defined by the response to the metric source,

$$
\delta W
=
\frac12\int d^d x\sqrt g\,
\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}
+\cdots,
$$

or equivalently

$$
\langle T^{\mu\nu}(x)\rangle
=
\frac{2}{\sqrt g}\frac{\delta W}{\delta g_{\mu\nu}(x)}.
$$

A local Weyl transformation is

$$
g_{\mu\nu}(x)\longrightarrow e^{2\sigma(x)}g_{\mu\nu}(x),
$$

so infinitesimally

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}.
$$

Plugging this into the metric variation gives

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma(x)\langle T^\mu{}_{\mu}(x)\rangle.
$$

Therefore Weyl invariance of the full quantum generating functional would imply

$$
\langle T^\mu{}_{\mu}\rangle=0
$$

as a local operator statement, up to contact terms. A Weyl anomaly is precisely the failure of this equation on curved space:

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle = \mathcal A[g,A,\lambda].
}
$$

Here $\mathcal A$ is a local scalar built from background sources. It is not an ordinary operator expectation value caused by a state. It is a property of how the CFT is defined in background fields.

<figure class="doc-figure" style="--figure-width: 34rem; --caption-width: 55rem;">

![The Weyl anomaly as the trace response of the connected generating functional.](/figures/cft/weyl-anomaly-logic.svg)

<figcaption>

The metric $g_{\mu\nu}$ is the source for $T_{\mu\nu}$. A Weyl variation $\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}$ probes the trace response $\langle T^\mu{}_{\mu}\rangle$. Classically this trace can vanish at a fixed point; quantum mechanically, in even spacetime dimension and on curved backgrounds, it may equal a local curvature functional $\mathcal A[g]$. In AdS/CFT the same local functional is encoded by the logarithmic counterterm of the regulated bulk action.

</figcaption>
</figure>

---

## The local Callan-Symanzik equation

Away from a fixed point, the trace of the stress tensor also contains beta functions. For scalar sources $\lambda^i(x)$ coupled to operators $\mathcal O_i$, the schematic local trace identity is

$$
\langle T^\mu{}_{\mu}\rangle
=
\beta^i(\lambda)\langle\mathcal O_i\rangle
+\mathcal A[g,\lambda]
+\text{contact terms}.
$$

At a CFT fixed point,

$$
\beta^i=0,
$$

but $\mathcal A[g]$ can remain nonzero on curved space. This is the key conceptual distinction:

$$
\boxed{
\text{nonzero }\beta^i
\quad\text{means RG running,}
\qquad
\mathcal A[g]\neq0
\quad\text{means anomalous Weyl response.}
}
$$

The Weyl anomaly is compatible with conformal invariance because it vanishes on flat space at separated points. It appears when the theory is coupled to background geometry, or equivalently when one asks for contact terms and finite parts of correlation functions involving stress tensors.

---

## What can an anomaly look like?

The anomaly density $\mathcal A$ must be local and have Weyl weight $d$, because

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\mathcal A
$$

is dimensionless. It must also satisfy Wess-Zumino consistency: two Weyl transformations commute,

$$
[\delta_{\sigma_1},\delta_{\sigma_2}]W=0.
$$

This severely restricts the possible terms.

For a CFT without boundary, the basic pattern is:

| Dimension | Local Weyl anomaly? | Typical data |
|---:|---|---|
| odd $d$ | no ordinary local anomaly | finite sphere free energy, parity-odd/contact subtleties |
| even $d$ | yes | Euler term, Weyl invariants, scheme-dependent total derivatives |

The phrase "no ordinary local anomaly" in odd dimensions assumes a closed manifold and no defects or boundaries. Boundaries and defects introduce additional anomaly structures.

There are three useful classes of anomaly terms.

**Type A anomalies** are proportional to the Euler density. In even dimension they are tied to topology and are controlled by a coefficient usually called $a$.

**Type B anomalies** are Weyl-invariant scalar densities, such as $W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}$ in four dimensions. Their coefficients are physical CFT data.

**Trivial anomalies** are Weyl variations of local counterterms. Their coefficients are scheme-dependent, because one can change them by changing the finite local terms used to define $W$.

---

## Two dimensions

In two dimensions the anomaly is fixed by one number, the central charge $c$:

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}R
}
$$

in the Euclidean sign convention used here. If another convention is used for $W$ or for the stress tensor, the overall sign may be reversed. The magnitude and the coefficient $c$ are invariant information.

The integrated Weyl variation is therefore

$$
\delta_\sigma W
=
-\frac{c}{24\pi}
\int d^2x\sqrt g\,\sigma R.
$$

For a constant Weyl rescaling, $\sigma=\sigma_0$, this becomes

$$
\delta_{\sigma_0} W
=
-\frac{c}{24\pi}\sigma_0\int d^2x\sqrt g\,R.
$$

Using Gauss-Bonnet,

$$
\int d^2x\sqrt g\,R=4\pi\chi(M),
$$

we get

$$
\delta_{\sigma_0}W
=
-\frac{c}{6}\chi(M)\sigma_0.
$$

On the sphere, $\chi(S^2)=2$, so a global change of radius has

$$
\delta_{\sigma_0}W_{S^2}
=
-\frac{c}{3}\sigma_0.
$$

This is a compact way to see that the central charge measures the response of the theory to changing the size of a curved two-dimensional space.

---

## The Polyakov action

The two-dimensional anomaly can be integrated to obtain the nonlocal Polyakov effective action. Its anomaly-sensitive part is

$$
W_{\rm anom}[g]
=
-\frac{c}{96\pi}
\int d^2x\sqrt g\,
R\frac{1}{\Box}R.
$$

This expression is nonlocal because the anomaly is local but cannot be written as the Weyl variation of a local diffeomorphism-invariant functional in two dimensions.

For a Weyl-related metric

$$
g_{\mu\nu}=e^{2\sigma}\hat g_{\mu\nu},
$$

the same information is often written in local Wess-Zumino form:

$$
\boxed{
W[e^{2\sigma}\hat g]-W[\hat g]
=
-\frac{c}{24\pi}
\int d^2x\sqrt{\hat g}\,
\left[(\hat\nabla\sigma)^2+\hat R\sigma\right].
}
$$

Varying this with respect to $\sigma$ gives

$$
\frac{\delta W}{\delta\sigma}
=
-\frac{c}{24\pi}\sqrt g\,R,
$$

which is exactly the two-dimensional trace anomaly.

This formula also explains why the cylinder vacuum energy knows about $c$. The map from the plane to the cylinder is a Weyl transformation plus a coordinate transformation. The anomalous part of the stress tensor transformation is the Schwarzian derivative. The same central charge controls both

$$
\langle T^\mu{}_{\mu}\rangle=-\frac{c}{24\pi}R
$$

and the cylinder Casimir energy

$$
E_0=-\frac{\pi c}{6L}.
$$

So the trace anomaly, the Schwarzian derivative, and the finite-size Casimir term are three faces of the same central charge.

---

## Four dimensions

In four-dimensional CFTs, the anomaly has the standard form

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle
=
\frac{1}{16\pi^2}
\left(
 c\,W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}
-a\,E_4
+b\,\Box R
\right)
}
$$

when no background flavor fields are turned on. Here

$$
E_4
=
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2
$$

is the four-dimensional Euler density, and $W_{\mu\nu\rho\sigma}$ is the Weyl tensor.

The coefficients $a$ and $c$ are physical. The coefficient $b$ is scheme-dependent. Indeed, adding a finite local counterterm

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

shifts the anomaly by a multiple of $\Box R$. Therefore $b$ is not intrinsic CFT data in the same sense as $a$ and $c$.

The $c$ coefficient controls the normalization of the stress-tensor two-point function in four dimensions. The $a$ coefficient controls the Euler anomaly and plays a deep role in RG flow; in unitary relativistic four-dimensional QFTs it decreases along RG flows from UV to IR. For holographic CFTs, both $a$ and $c$ are read from the bulk gravitational action.

With background gauge fields for global symmetries, additional terms may appear, schematically

$$
\mathcal A[g,A]
\supset
\kappa_{ab}\,F^a_{\mu\nu}F^{b\mu\nu},
$$

with normalization depending on the convention for the current two-point function and for the background gauge field. These terms encode flavor-current data and, in supersymmetric theories, often sit in the same multiplets as ordinary 't Hooft anomalies.

---

## Scheme dependence and contact terms

A useful rule of thumb is:

$$
\boxed{
\text{separated-point correlators are universal; contact terms require a scheme.}
}
$$

The generating functional $W[g,A,\lambda]$ is defined only after choosing local counterterms. Finite counterterms can change local terms in the anomaly and contact terms in stress-tensor correlators. They cannot change the nontrivial anomaly coefficients such as $c$ in two dimensions or $a,c$ in four dimensions.

For example, the four-dimensional counterterm

$$
\int d^4x\sqrt g\,R^2
$$

is local and diffeomorphism invariant. Its Weyl variation is also local, so it shifts a local anomaly term. This is why the $\Box R$ term is called trivial. By contrast, the Euler term and the Weyl-squared term cannot be removed by finite local counterterms without changing the theory.

This distinction is especially important in AdS/CFT. Holographic renormalization requires adding counterterms at the radial cutoff. Power-law counterterms remove power divergences. Logarithmic counterterms encode anomalies. Finite counterterms change the renormalization scheme but not the nontrivial anomaly coefficients.

---

## Holographic origin of the anomaly

Use Fefferman-Graham coordinates near the boundary of an asymptotically AdS$_{d+1}$ spacetime:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{\mu\nu}(z,x)dx^\mu dx^\nu\right),
$$

with boundary metric

$$
g_{\mu\nu}^{(0)}(x)=\lim_{z\to0}g_{\mu\nu}(z,x).
$$

Regulate the bulk at $z=\epsilon$. The on-shell action has divergences as $\epsilon\to0$:

$$
S_{\rm os}(\epsilon)
=
\frac{S_{(d)}}{\epsilon^d}
+\frac{S_{(d-2)}}{\epsilon^{d-2}}
+\cdots
+S_{\log}\log(\epsilon\mu)
+S_{\rm finite}.
$$

For even boundary dimension $d$, the logarithmic term is present. Its coefficient is local in the boundary sources and gives the Weyl anomaly. Schematically,

$$
S_{\log}
=
\int d^d x\sqrt{g^{(0)}}\,\mathcal L_{\log}[g^{(0)},\text{sources}],
$$

and

$$
\mathcal A[g^{(0)}]
\quad\text{is determined by}\quad
\mathcal L_{\log}.
$$

The reason is geometric. A boundary Weyl transformation is realized in the bulk by a radial diffeomorphism, roughly

$$
z\to e^{-\sigma(x)}z,
\qquad
 g_{\mu\nu}^{(0)}\to e^{2\sigma(x)}g_{\mu\nu}^{(0)}.
$$

Power divergences can be subtracted covariantly. The logarithmic term is different: under a Weyl rescaling, $\log\epsilon$ shifts by a finite amount. That finite shift is exactly the anomaly.

Two famous holographic examples are:

$$
\text{AdS}_3/\text{CFT}_2:
\qquad
c=\frac{3L}{2G_3},
$$

and, for five-dimensional Einstein gravity dual to a four-dimensional CFT,

$$
\text{AdS}_5/\text{CFT}_4:
\qquad
 a=c=\frac{\pi L^3}{8G_5}.
$$

Higher-derivative terms in the bulk action generally make $a$ and $c$ differ. Thus the equality $a=c$ is not a theorem of all holographic CFTs; it is a special feature of the simplest two-derivative Einstein gravity duals.

---

## Weyl anomaly versus global conformal symmetry

A common confusion is to think that a Weyl anomaly destroys conformal invariance. It does not, at least not in the flat-space sense relevant for ordinary CFT correlators.

On flat space without sources,

$$
R_{\mu\nu\rho\sigma}=0,
\qquad
F_{\mu\nu}=0,
$$

so the local curvature anomaly vanishes:

$$
\mathcal A[\mathbb R^d]=0.
$$

The separated-point conformal Ward identities on flat space remain valid. What changes is the curved-space generating functional and the contact terms obtained by differentiating it with respect to the metric.

This is why the anomaly is often invisible in elementary flat-space correlators but unavoidable in stress-tensor physics. In two dimensions, $c$ appears both in the $T(z)T(0)$ OPE and in the trace anomaly. In four dimensions, $a$ and $c$ appear in stress-tensor correlators, entanglement across spheres, and curved-space partition functions.

---

## AdS/CFT checkpoint

The Weyl anomaly is one of the sharpest tests of the AdS/CFT dictionary because it compares a purely quantum CFT effect with a classical bulk computation.

On the CFT side:

$$
\delta_\sigma W_{\rm CFT}[g]
=
\int d^d x\sqrt g\,\sigma\mathcal A[g].
$$

On the bulk side:

$$
W_{\rm CFT}[g]
\simeq
S_{\rm ren}^{\rm os}[g],
$$

and the anomalous Weyl variation comes from logarithmic counterterms in $S_{\rm ren}^{\rm os}$. The radial cutoff remembers the boundary scale. This is the gravitational version of renormalization.

For later AdS/CFT applications, remember the following dictionary:

$$
\begin{array}{ccl}
\text{boundary Weyl rescaling} &\longleftrightarrow& \text{bulk radial diffeomorphism},\\
\text{CFT trace anomaly} &\longleftrightarrow& \text{bulk logarithmic divergence},\\
 c_{2d},\ a_{4d},\ c_{4d} &\longleftrightarrow& \text{coefficients in the bulk action},\\
\text{scheme-dependent contact terms} &\longleftrightarrow& \text{finite local counterterms}.
\end{array}
$$

This is why every serious holographic computation of stress tensors or partition functions includes holographic renormalization.

---

## Common pitfalls

The first pitfall is to confuse a Weyl anomaly with RG running. A nonzero beta function means the theory is not at a fixed point. A Weyl anomaly can exist even at an exact fixed point when the theory is placed on a curved background.

The second pitfall is to treat all anomaly terms as equally physical. In four dimensions, $a$ and $c$ are intrinsic; the coefficient of $\Box R$ is not. Finite local counterterms can shift it.

The third pitfall is to forget contact terms. Differentiating the anomaly with respect to $g_{\mu\nu}$ gives contact contributions to stress-tensor correlators. These are essential for Ward identities, even though they may not affect separated-point correlators.

The fourth pitfall is to assume odd-dimensional CFTs have no universal curved-space data. They have no ordinary local Weyl anomaly on closed manifolds, but they can still have universal finite quantities, such as the sphere free energy in three dimensions.

---

## Exercises

### Exercise 1 — Weyl variation and the stress-tensor trace

Using

$$
\delta W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu},
$$

show that an infinitesimal Weyl transformation $\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}$ gives

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute

$$
\delta g_{\mu\nu}=2\sigma g_{\mu\nu}
$$

into the variation of $W$:

$$
\delta_\sigma W
=
\frac12\int d^d x\sqrt g\,\langle T^{\mu\nu}\rangle 2\sigma g_{\mu\nu}.
$$

The factor of $2$ cancels the $1/2$, and

$$
g_{\mu\nu}\langle T^{\mu\nu}\rangle
=
\langle T^\mu{}_{\mu}\rangle.
$$

Therefore

$$
\delta_\sigma W
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

</details>

### Exercise 2 — Integrated two-dimensional anomaly

For a two-dimensional CFT with

$$
\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}R,
$$

show that a constant Weyl rescaling $g_{\mu\nu}\to e^{2\sigma_0}g_{\mu\nu}$ changes $W$ by

$$
\delta_{\sigma_0}W
=
-\frac{c}{6}\chi(M)\sigma_0.
$$

<details>
<summary><strong>Solution</strong></summary>

For constant $\sigma_0$,

$$
\delta_{\sigma_0}W
=
\int d^2x\sqrt g\,\sigma_0\langle T^\mu{}_{\mu}\rangle.
$$

Using the anomaly,

$$
\delta_{\sigma_0}W
=
-\frac{c}{24\pi}\sigma_0\int d^2x\sqrt g\,R.
$$

Gauss-Bonnet gives

$$
\int d^2x\sqrt g\,R=4\pi\chi(M).
$$

Hence

$$
\delta_{\sigma_0}W
=
-\frac{c}{24\pi}\sigma_0(4\pi\chi(M))
=
-\frac{c}{6}\chi(M)\sigma_0.
$$

</details>

### Exercise 3 — Vary the Polyakov Wess-Zumino action

Let

$$
W[e^{2\sigma}\hat g]-W[\hat g]
=
-\frac{c}{24\pi}
\int d^2x\sqrt{\hat g}\,
\left[(\hat\nabla\sigma)^2+\hat R\sigma\right].
$$

Show that varying with respect to $\sigma$ gives the trace anomaly

$$
\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}R[g].
$$

<details>
<summary><strong>Solution</strong></summary>

Vary the Wess-Zumino action:

$$
\delta W
=
-\frac{c}{24\pi}
\int d^2x\sqrt{\hat g}\,
\left[2\hat\nabla_\mu\sigma\hat\nabla^\mu\delta\sigma+\hat R\delta\sigma\right].
$$

Integrating by parts gives

$$
\delta W
=
-\frac{c}{24\pi}
\int d^2x\sqrt{\hat g}\,
\left[-2\hat\Box\sigma+\hat R\right]\delta\sigma.
$$

For $g_{\mu\nu}=e^{2\sigma}\hat g_{\mu\nu}$ in two dimensions,

$$
\sqrt g\,R[g]
=
\sqrt{\hat g}\left(\hat R-2\hat\Box\sigma\right).
$$

Thus

$$
\delta W
=
-\frac{c}{24\pi}
\int d^2x\sqrt g\,R[g]\,\delta\sigma.
$$

Comparing with

$$
\delta W
=
\int d^2x\sqrt g\,\delta\sigma\langle T^\mu{}_{\mu}\rangle
$$

gives

$$
\langle T^\mu{}_{\mu}\rangle
=
-\frac{c}{24\pi}R[g].
$$

</details>

### Exercise 4 — Why $\Box R$ is scheme-dependent in four dimensions

Show that adding

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

shifts the four-dimensional Weyl anomaly by a term proportional to $\Box R$.

<details>
<summary><strong>Solution</strong></summary>

In $d$ dimensions,

$$
\delta_\sigma\sqrt g=d\sigma\sqrt g,
$$

and

$$
\delta_\sigma R=-2\sigma R-2(d-1)\Box\sigma.
$$

In $d=4$,

$$
\delta_\sigma(\sqrt g R^2)
=
\sqrt g\left(4\sigma R^2+2R\delta_\sigma R\right).
$$

Substituting $\delta_\sigma R=-2\sigma R-6\Box\sigma$ gives

$$
\delta_\sigma(\sqrt g R^2)
=
\sqrt g\left(4\sigma R^2-4\sigma R^2-12R\Box\sigma\right)
=
-12\sqrt g\,R\Box\sigma.
$$

On a closed manifold, integrate by parts:

$$
\int d^4x\sqrt g\,R\Box\sigma
=
\int d^4x\sqrt g\,\sigma\Box R.
$$

Therefore

$$
\delta_\sigma\Delta W
=
-12\alpha\int d^4x\sqrt g\,\sigma\Box R.
$$

So the anomaly shifts by

$$
\Delta\mathcal A=-12\alpha\Box R.
$$

This proves that the coefficient of $\Box R$ depends on the finite local counterterm convention.

</details>

### Exercise 5 — The Euler anomaly on $S^4$

Assume a four-dimensional CFT on a conformally flat closed manifold, so $W_{\mu\nu\rho\sigma}=0$, and ignore the scheme-dependent $\Box R$ term. Use

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{a}{16\pi^2}E_4
$$

and

$$
\int d^4x\sqrt g\,E_4=32\pi^2\chi(M)
$$

to find the change of $W$ under a constant Weyl rescaling.

<details>
<summary><strong>Solution</strong></summary>

For constant $\sigma_0$,

$$
\delta_{\sigma_0}W
=
\int d^4x\sqrt g\,\sigma_0\langle T^\mu{}_{\mu}\rangle.
$$

Substituting the Euler anomaly gives

$$
\delta_{\sigma_0}W
=
-\frac{a}{16\pi^2}\sigma_0
\int d^4x\sqrt g\,E_4.
$$

Using Gauss-Bonnet in four dimensions,

$$
\delta_{\sigma_0}W
=
-\frac{a}{16\pi^2}\sigma_0(32\pi^2\chi(M))
=
-2a\chi(M)\sigma_0.
$$

For $S^4$, $\chi(S^4)=2$, so

$$
\delta_{\sigma_0}W_{S^4}
=
-4a\sigma_0.
$$

</details>

### Exercise 6 — Why the holographic anomaly comes from a logarithm

Suppose the regulated bulk on-shell action contains

$$
S_{\log}=\log(\epsilon\mu)
\int d^d x\sqrt{g^{(0)}}\,\mathcal L_{\log}[g^{(0)}].
$$

Explain why this term can produce a finite Weyl anomaly after renormalization.

<details>
<summary><strong>Solution</strong></summary>

A boundary Weyl transformation is equivalent near the boundary to a radial rescaling of the cutoff,

$$
\epsilon\to e^{-\sigma}\epsilon,
$$

at least for constant $\sigma$ and locally for general $\sigma(x)$. Therefore

$$
\log(\epsilon\mu)
\to
\log(\epsilon\mu)-\sigma.
$$

The logarithmic counterterm shifts by a finite amount,

$$
\delta_\sigma S_{\log}
=
-\int d^d x\sqrt{g^{(0)}}\,\sigma\mathcal L_{\log}.
$$

After the divergent part has been subtracted, this finite shift remains. It is interpreted as the Weyl variation of the renormalized CFT generating functional:

$$
\delta_\sigma W_{\rm CFT}
=
\int d^d x\sqrt{g^{(0)}}\,\sigma\mathcal A[g^{(0)}].
$$

Thus $\mathcal A$ is determined by the coefficient of the logarithmic term, up to sign conventions in the definition of $W$ and counterterms.

</details>

---

## Takeaway

The Weyl anomaly is the curved-space remnant of scale symmetry after quantization:

$$
\boxed{
\langle T^\mu{}_{\mu}\rangle=0\quad\text{on flat space at a fixed point,}
\qquad
\langle T^\mu{}_{\mu}\rangle=\mathcal A[g]\quad\text{on curved space.}
}
$$

In two dimensions, $\mathcal A$ is controlled by $c$. In four dimensions, it is controlled by $a$, $c$, and scheme-dependent local terms. In AdS/CFT, the anomaly is the finite Weyl variation left behind by logarithmic divergences of the bulk on-shell action.

## Further reading

For the two-dimensional trace anomaly, the Polyakov action, and the relation to the stress tensor, see standard 2D CFT references, especially the sections on the central charge, trace anomaly, and finite-size effects. For four-dimensional anomalies and holographic renormalization, the natural next references are reviews of conformal anomalies, local RG, and holographic counterterms. The next page uses the same source-functional logic to study thermal CFT.
