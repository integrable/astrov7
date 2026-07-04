---
title: "Variational Principles and Boundary Terms"
description: "A working reference for AdS/CFT variational principles: scalar, Maxwell, gravitational, fermionic, counterterm, Legendre-transform, and mixed-boundary-condition terms."
sidebar:
  order: 40
---

A holographic calculation is only as good as its variational principle. The equations of motion determine the bulk solution, but the boundary terms determine what data are held fixed, what quantity is interpreted as the response, which thermodynamic ensemble is being used, and whether the on-shell action is finite.

The guiding rule is simple:

$$
\text{sources are the variables held fixed at the boundary,}
\qquad
\text{one-point functions are conjugate momenta after renormalization.}
$$

This appendix collects the boundary terms used repeatedly in the course. The formulas are written for the most common AdS/CFT conventions. Signs can change with Lorentzian versus Euclidean signature, outward-normal conventions, and whether one varies $\gamma_{ij}$ or $\gamma^{ij}$. The safest practice is always to vary the action explicitly.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A flowchart showing how bulk actions, boundary terms, counterterms, and optional Legendre or mixed terms produce a well-posed variational principle and finite one-point functions.](/figures/course/variational-principles-boundary-terms.svg)

<figcaption>

A holographic variational principle has three layers: the bulk action gives equations of motion, boundary terms make the chosen boundary conditions well posed, and counterterms make the on-shell variation finite. Optional Legendre or mixed terms change the ensemble or boundary condition.

</figcaption>
</figure>

## The general structure

For any bulk field $\Phi$, the variation of the action has the schematic form

$$
\delta S
=
\int_M E_\Phi\,\delta\Phi
+
\int_{\partial M}\Theta(\Phi,\delta\Phi).
$$

Here $E_\Phi=0$ gives the equations of motion, while $\Theta$ is the boundary variation. On shell,

$$
\delta S_{\text{on-shell}}
=
\int_{\partial M}\Theta(\Phi,\delta\Phi).
$$

A well-posed variational principle for Dirichlet data has the form

$$
\delta S_{\text{ren,on-shell}}
=
\int_{\partial M} d^d x\sqrt{|g_{(0)}|}\,
\langle \mathcal O_A\rangle\,\delta J^A,
$$

where $J^A$ are sources held fixed at the boundary. If $\delta J^A=0$, the on-shell variation vanishes.

Changing boundary terms changes the variational problem. It can turn Dirichlet data into Neumann data, impose mixed boundary conditions, or switch between grand-canonical and canonical ensembles.

## Cutoff surfaces and outward normals

In holographic renormalization, one introduces a cutoff surface near the boundary. In Poincare coordinates,

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+g_{ij}(z,x)dx^idx^j\right),
$$

one often regulates the geometry at

$$
z=\epsilon.
$$

The regulated bulk region is $z\ge \epsilon$, so the outward-pointing unit normal toward the AdS boundary is

$$
n^a\partial_a=-\frac{z}{L}\partial_z
\qquad
\text{at }z=\epsilon.
$$

In $r$ coordinates, where the boundary is $r\to\infty$, the regulated region is usually $r\le r_c$, and the outward normal points toward increasing $r$.

The induced metric on the cutoff surface is denoted $\gamma_{ij}$. The boundary metric source is obtained after a Weyl rescaling and a limit, for example

$$
g_{(0)ij}
=
\lim_{\epsilon\to0}\frac{\epsilon^2}{L^2}\gamma_{ij}.
$$

## Scalar fields

Consider a Euclidean scalar action

$$
S_\phi
=
\frac12\int_M d^{d+1}x\sqrt{g}
\left(g^{ab}\partial_a\phi\partial_b\phi+m^2\phi^2\right).
$$

Its variation is

$$
\delta S_\phi
=
\int_M d^{d+1}x\sqrt{g}\,(-\nabla^2\phi+m^2\phi)\delta\phi
+
\int_{\partial M} d^d x\sqrt{\gamma}\,n^a\partial_a\phi\,\delta\phi.
$$

The bare canonical momentum is therefore

$$
\Pi_\phi
=
\sqrt{\gamma}\,n^a\partial_a\phi.
$$

Near the AdS boundary, a scalar behaves schematically as

$$
\phi(z,x)
=
z^{d-\Delta}\phi_{(0)}(x)
+
\cdots
+
z^\Delta A(x)
+
\cdots,
$$

with

$$
m^2L^2=\Delta(\Delta-d).
$$

The raw momentum $\Pi_\phi$ diverges as the cutoff is removed. Counterterms define a renormalized momentum,

$$
\Pi_{\phi,\mathrm{ren}}
=
\frac{\delta S_{\mathrm{ren}}}{\delta\phi_{(0)}}.
$$

The standard-quantization one-point function is

$$
\langle\mathcal O\rangle
=
\frac{1}{\sqrt{|g_{(0)}|}}
\frac{\delta S_{\mathrm{ren}}}{\delta\phi_{(0)}}.
$$

For a simple scalar without derivative sources, the nonlocal part is proportional to the normalizable coefficient $A(x)$, but local terms may be added by counterterms or finite scheme choices.

## Scalar boundary conditions

There are three common scalar boundary conditions.

| Boundary condition | Fixed data | Boundary interpretation | Typical action |
|---|---|---|---|
| Dirichlet | $\phi_{(0)}$ | source for $\mathcal O$ | $S_{\mathrm{ren}}$ |
| Neumann / alternate | renormalized momentum | source for alternate operator | Legendre-transformed action |
| mixed | relation between $\phi_{(0)}$ and momentum | multi-trace deformation | $S_{\mathrm{ren}}+\int W(\phi_{(0)})$ |

For alternate quantization one performs a Legendre transform. Schematically,

$$
\widetilde S_{\mathrm{ren}}
=
S_{\mathrm{ren}}
-
\int d^d x\sqrt{|g_{(0)}|}\,\phi_{(0)}\langle\mathcal O\rangle,
$$

where the precise normalization depends on how the source and response have been normalized.

For mixed boundary conditions, one adds a boundary functional

$$
S_W
=
\int d^d x\sqrt{|g_{(0)}|}\,W(\phi_{(0)}),
$$

so that the boundary condition becomes, schematically,

$$
\langle\mathcal O\rangle+W'(\phi_{(0)})=0
$$

when no external source is present. In the CFT this corresponds to a multi-trace deformation.

## Maxwell fields

For a bulk gauge field,

$$
S_A
=
-\frac{1}{4g_F^2}
\int_M d^{d+1}x\sqrt{-g}\,F_{ab}F^{ab},
\qquad
F=dA.
$$

The on-shell variation is

$$
\delta S_A\big|_{\text{on-shell}}
=
-\frac{1}{g_F^2}
\int_{\partial M}d^d x\sqrt{|\gamma|}\,n_aF^{ai}\delta A_i.
$$

Thus the bare canonical momentum is

$$
\Pi_A^i
=
-\frac{\sqrt{|\gamma|}}{g_F^2}n_aF^{ai}.
$$

After adding counterterms and taking the limit,

$$
\langle J^i\rangle
=
\frac{1}{\sqrt{|g_{(0)}|}}
\frac{\delta S_{\mathrm{ren}}}{\delta A_{(0)i}}.
$$

For finite density, the near-boundary temporal component often has the form

$$
A_t(z)=\mu-\rho\,z^{d-2}+\cdots,
$$

for $d>2$ in a simple Maxwell theory. The coefficient $\mu$ is the chemical potential, while the canonical momentum is proportional to the charge density.

Dirichlet boundary conditions fix $A_{(0)i}$. For $A_t$, this is the grand-canonical ensemble: the chemical potential is fixed. A Neumann or Legendre-transformed action fixes charge density instead and corresponds to a canonical ensemble.

Gauge fields also require a conceptual boundary condition: gauge transformations that do not vanish at the boundary act as global symmetries of the CFT. The boundary value $A_{(0)i}$ is a background source for that global current, not a dynamical gauge field unless one explicitly changes the boundary theory.

## Chern–Simons and topological terms

In odd bulk dimensions one may have Chern–Simons terms, for example

$$
S_{\mathrm{CS}}
\sim
\int A\wedge F\wedge F.
$$

Such terms modify the canonical momentum and can produce anomalies in the boundary current. The general rule is unchanged: vary the full action, including topological terms and any required boundary terms, then identify the finite coefficient of $\delta A_{(0)i}$.

Do not compute currents from the Maxwell term alone if Chern–Simons terms are present.

## Gravity: why the GHY term is needed

The Einstein–Hilbert action is

$$
S_{\mathrm{EH}}
=
\frac{1}{16\pi G_{d+1}}
\int_M d^{d+1}x\sqrt{|g|}\,(R-2\Lambda).
$$

Its variation contains second-derivative boundary terms. Schematically,

$$
\delta S_{\mathrm{EH}}
=
\frac{1}{16\pi G_{d+1}}
\int_M\sqrt{|g|}\,E_{ab}\delta g^{ab}
+
\frac{1}{16\pi G_{d+1}}
\int_{\partial M}\sqrt{|\gamma|}\,n^a
\left(\nabla^b\delta g_{ab}-g^{bc}\nabla_a\delta g_{bc}\right).
$$

This is not a good Dirichlet variational principle for the induced metric $\gamma_{ij}$, because the boundary variation contains normal derivatives of $\delta g_{ab}$.

The remedy is the Gibbons–Hawking–York term

$$
S_{\mathrm{GHY}}
=
\frac{1}{8\pi G_{d+1}}
\int_{\partial M}d^d x\sqrt{|\gamma|}\,K,
$$

where

$$
K=\gamma^{ij}K_{ij},
\qquad
K_{ij}=\gamma_i{}^a\gamma_j{}^b\nabla_a n_b.
$$

For a radial AdS cutoff boundary with spacelike outward normal, this sign convention is the one used throughout the course. If the boundary contains spacelike initial/final slices or null/corner pieces, additional signs and corner terms must be handled separately.

On shell, the variation of $S_{\mathrm{EH}}+S_{\mathrm{GHY}}$ becomes

$$
\delta(S_{\mathrm{EH}}+S_{\mathrm{GHY}})_{\text{on-shell}}
=
\frac{1}{16\pi G_{d+1}}
\int_{\partial M}d^d x\sqrt{|\gamma|}\,
\left(K^{ij}-K\gamma^{ij}\right)\delta\gamma_{ij}.
$$

The corresponding bare Brown–York tensor is

$$
T^{ij}_{\mathrm{BY,bare}}
=
\frac{1}{8\pi G_{d+1}}
\left(K^{ij}-K\gamma^{ij}\right).
$$

In asymptotically AdS spacetimes this diverges as the cutoff is removed. Holographic counterterms are needed.

## Gravitational counterterms

The renormalized gravitational action has the schematic form

$$
S_{\mathrm{ren}}
=
\lim_{\epsilon\to0}
\left(
S_{\mathrm{EH}}^{z\ge\epsilon}
+
S_{\mathrm{GHY}}^{z=\epsilon}
+
S_{\mathrm{ct}}^{z=\epsilon}
\right).
$$

For asymptotically AdS Einstein gravity, the first counterterms are

$$
S_{\mathrm{ct}}
=
-\frac{1}{8\pi G_{d+1}}
\int_{z=\epsilon}d^d x\sqrt{|\gamma|}
\left[
\frac{d-1}{L}
+
\frac{L}{2(d-2)}R[\gamma]
+\cdots
\right],
$$

for $d>2$, with additional curvature-squared and logarithmic terms in higher dimensions. The pole at $d=2$ is a warning that the two-dimensional case has a logarithmic Weyl-anomaly structure and should be treated separately.

The renormalized stress tensor is

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta S_{\mathrm{ren}}}{\delta g_{(0)ij}}.
$$

Equivalently, it is the finite rescaled limit of the Brown–York tensor plus counterterm contributions.

## Boundary terms for fermions

Fermionic actions are first order, so their variational principles differ from scalar and Maxwell fields. A bulk Dirac action has the schematic form

$$
S_\psi
=
\int_M d^{d+1}x\sqrt{|g|}\,\bar\psi(\Gamma^aD_a-m)\psi
+S_{\partial\psi}.
$$

Near the boundary, decompose the spinor into radial eigenspaces,

$$
\psi=\psi_+ + \psi_-,
\qquad
\Gamma^{\hat r}\psi_\pm=\pm\psi_\pm.
$$

The boundary variation pairs $\psi_+$ and $\psi_-$. One fixes only half of the spinor data; the other half is the conjugate response. The boundary term $S_{\partial\psi}$ selects which half is held fixed and determines the sign and normalization of the fermionic two-point function.

The key lesson is not to impose Dirichlet boundary conditions on all spinor components. First-order equations do not allow that.

## Boundary terms and ensembles

Boundary terms encode ensembles. The same bulk equations can describe different boundary theories or different thermodynamic ensembles depending on the boundary term.

| Bulk field | Dirichlet data | Response | Alternative boundary term | Boundary meaning |
|---|---|---|---|---|
| scalar $\phi$ | $\phi_{(0)}$ | $\langle\mathcal O\rangle$ | Legendre or $W(\phi_{(0)})$ | alternate quantization or multi-trace deformation |
| gauge field $A_i$ | $A_{(0)i}$ | $\langle J^i\rangle$ | Legendre transform in $A_i$ | fixed charge/current ensemble |
| metric $g_{ij}$ | $g_{(0)ij}$ | $\langle T^{ij}\rangle$ | Neumann/mixed gravity terms | dynamical boundary gravity or stress-tensor deformation |
| spinor $\psi$ | half of radial spinor data | conjugate half | alternate spinor boundary term | alternate fermion quantization |

For most of this course, the default is Dirichlet boundary conditions for the boundary metric and background sources, plus the counterterms required by holographic renormalization.

## Corners, joints, and null boundaries

The basic GHY term assumes a smooth non-null boundary. If the boundary is piecewise smooth, additional joint or corner terms may be required. If the boundary includes null segments, the appropriate boundary terms involve the null generator, its non-affinity, and possible joint terms.

These terms are essential in some modern topics, especially gravitational complexity and finite-region actions. They are usually not needed for the foundational AdS/CFT calculations in this course, where the regulator surface is a smooth radial cutoff and the horizon is handled by regularity or infalling conditions rather than by treating it as a boundary of the variational problem.

## Practical recipe

When setting up a holographic calculation, use this checklist.

1. **Choose the field content and action.** Include all bulk terms relevant to the correlator or thermodynamic quantity.
2. **Choose the boundary data.** Decide which coefficients are sources and which ensemble is intended.
3. **Vary the action.** Identify the boundary term in $\delta S$.
4. **Add terms for a well-posed variational principle.** For gravity this includes $S_{\mathrm{GHY}}$; for other fields this may include Legendre or mixed terms.
5. **Add counterterms.** Remove cutoff divergences by local covariant terms on the cutoff surface.
6. **Take the finite variation.** The coefficients of source variations are the renormalized one-point functions.
7. **Check Ward identities.** Diffeomorphism, gauge, and Weyl identities are the best way to catch missing boundary terms or sign errors.

## Common confusions

### “The GHY term is a counterterm.”

No. The GHY term makes the Dirichlet gravitational variational principle well posed. It does not by itself cancel AdS divergences. Holographic counterterms are additional local functionals of the induced fields.

### “The horizon is a boundary where I should fix data.”

For ordinary thermal AdS/CFT correlators, the horizon is not a boundary of the variational problem in the same sense as the AdS boundary. In Euclidean signature one imposes smoothness. In Lorentzian retarded problems one imposes infalling regularity.

### “Changing a boundary term is just a convention.”

Some finite local counterterms are scheme choices. But Legendre transforms and mixed boundary terms can change the physical boundary condition and hence the dual theory or ensemble.

### “The canonical momentum is automatically the vev.”

The bare canonical momentum usually diverges near the AdS boundary. The vev is the **renormalized** canonical momentum, possibly with local finite contributions depending on scheme.

## Exercises

### Exercise 1: Scalar boundary variation

Starting from

$$
S_\phi
=
\frac12\int_M\sqrt{g}\left((\nabla\phi)^2+m^2\phi^2\right),
$$

show that the on-shell variation is

$$
\delta S_\phi\big|_{\text{on-shell}}
=
\int_{\partial M}\sqrt{\gamma}\,n^a\partial_a\phi\,\delta\phi.
$$

<details>
<summary><strong>Solution</strong></summary>

Varying the action gives

$$
\delta S_\phi
=
\int_M\sqrt{g}\left(\nabla^a\phi\nabla_a\delta\phi+m^2\phi\delta\phi\right).
$$

Integrating the first term by parts,

$$
\int_M\sqrt{g}\,\nabla^a\phi\nabla_a\delta\phi
=
-\int_M\sqrt{g}\,(\nabla^2\phi)\delta\phi
+
\int_{\partial M}\sqrt{\gamma}\,n^a\partial_a\phi\,\delta\phi.
$$

Thus

$$
\delta S_\phi
=
\int_M\sqrt{g}\,(-\nabla^2\phi+m^2\phi)\delta\phi
+
\int_{\partial M}\sqrt{\gamma}\,n^a\partial_a\phi\,\delta\phi.
$$

On shell, the bulk term vanishes.

</details>

### Exercise 2: Maxwell charge density

For a Maxwell field with only $A_t(z)$ nonzero in a diagonal black-brane background, show that the radial canonical momentum is independent of $z$ on shell.

<details>
<summary><strong>Solution</strong></summary>

The Maxwell equation is

$$
\nabla_aF^{at}=0.
$$

Equivalently,

$$
\partial_a\left(\sqrt{-g}F^{at}\right)=0.
$$

If the field depends only on $z$, this becomes

$$
\partial_z\left(\sqrt{-g}F^{zt}\right)=0.
$$

Therefore

$$
\sqrt{-g}F^{zt}=\text{constant}.
$$

Up to the factor $-1/g_F^2$ and the cutoff normal convention, this constant is the radial canonical momentum conjugate to $A_t$. Holographically it is the conserved charge density.

</details>

### Exercise 3: Why the GHY term is needed

Why is the Einstein–Hilbert action alone not a well-posed Dirichlet variational principle for the metric?

<details>
<summary><strong>Solution</strong></summary>

The Ricci scalar contains second derivatives of the metric. When the Einstein–Hilbert action is varied and integrations by parts are performed, the boundary variation contains normal derivatives of $\delta g_{ab}$. Dirichlet boundary conditions fix the induced metric variation $\delta\gamma_{ij}$ at the boundary, but they do not fix its normal derivative. Therefore the on-shell variation of the Einstein–Hilbert action alone does not vanish under Dirichlet boundary conditions.

The GHY term cancels precisely these unwanted normal-derivative terms. The combined action $S_{\mathrm{EH}}+S_{\mathrm{GHY}}$ has an on-shell boundary variation proportional to $\delta\gamma_{ij}$, so fixing the induced metric gives a well-posed variational principle.

</details>

## Further reading

- J. W. York, [Role of Conformal Three-Geometry in the Dynamics of Gravitation](https://doi.org/10.1103/PhysRevLett.28.1082).
- G. W. Gibbons and S. W. Hawking, [Action Integrals and Partition Functions in Quantum Gravity](https://doi.org/10.1103/PhysRevD.15.2752).
- J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
