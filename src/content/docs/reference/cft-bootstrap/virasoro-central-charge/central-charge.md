---
title: "Central Charge"
description: "Explains the central charge in two-dimensional CFT through the stress-tensor OPE, Virasoro algebra, Schwarzian transformation, trace anomaly, and finite-size energy."
sidebar:
  label: "Central Charge"
  order: 2
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Belavin–Polyakov–Zamolodchikov 1984; Cardy 1984; Zamolodchikov 1986"
topics:
  - central charge
  - two-dimensional CFT
  - Virasoro algebra
  - conformal anomaly
  - stress tensor
  - cylinder vacuum energy
canonicalTopics:
  - central-charge
  - conformal-anomaly
  - virasoro-central-extension
researchStatus:
  established:
    - "In two-dimensional CFT, the central charge is a convention-fixed datum appearing in the stress-tensor two-point function, the Virasoro central extension, the Schwarzian transformation law, and the conformal anomaly."
  active:
    - "Central charge remains central in modular bootstrap, logarithmic CFT, nonunitary CFT, holography, and chiral phases where c and c-bar need not coincide."
---

## Summary

The **central charge** $c$ is the number that measures the central extension of local conformal symmetry in the holomorphic sector of a two-dimensional CFT. In the conventions of this chapter,

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w},
$$

and therefore

$$
[L_m,L_n]
=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The antiholomorphic sector has its own central charge $\bar c$.

The central charge is not just an algebraic decoration. The same $c$ appears in the stress-tensor two-point function, the Schwarzian derivative in the conformal transformation of $T$, the cylinder vacuum energy, the trace anomaly on curved two-dimensional backgrounds, and the asymptotic growth of states. This is one of the reasons 2D CFT is unusually coherent: several phenomena that look different are controlled by one datum.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Central charge dictionary](/figures/cft-bootstrap/central-charge-dictionary.svg)

<figcaption>

The same central charge $c$ appears in several equivalent guises: the $TT$ OPE, the Virasoro algebra, the Schwarzian transformation law, cylinder vacuum energy, and the trace anomaly.

</figcaption>
</figure>

## Prerequisites

You should first read [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), and [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/). The page also uses the primary-field convention from [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/).

No curved-spacetime machinery is required for the main formulas, but the trace-anomaly interpretation is easiest if you are comfortable with the idea that the stress tensor is obtained by varying the action with respect to the metric.

## Core idea

Classically, local holomorphic conformal transformations form the Witt algebra. Quantum mechanically, the corresponding stress-tensor charges can realize a **central extension**. The extension is central because the new term commutes with all generators; it is an ordinary number in any irreducible representation.

The central charge is the coefficient of that extension. Once the normalization of $T$ is fixed by Ward identities, $c$ is physical data of the CFT.

The useful dictionary is

$$
\begin{array}{ccl}
\text{stress tensor two-point function} & \Longleftrightarrow & c,\\
\text{Virasoro central extension} & \Longleftrightarrow & c,\\
\text{Schwarzian transformation of }T & \Longleftrightarrow & c,\\
\text{cylinder Casimir energy} & \Longleftrightarrow & c,\\
\text{two-dimensional trace anomaly} & \Longleftrightarrow & c.
\end{array}
$$

Different conventions move factors of $2\pi$, signs, and metric factors around. The CFT-normalized OPE above is the convention used in this chapter.

## Setup and conventions

The holomorphic and antiholomorphic stress tensors are expanded as

$$
T(z)=\sum_{n\in\mathbb Z}L_n z^{-n-2},
\qquad
\bar T(\bar z)=\sum_{n\in\mathbb Z}\bar L_n \bar z^{-n-2}.
$$

The Virasoro algebras are

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

$$
[\bar L_m,\bar L_n]=(m-n)\bar L_{m+n}+\frac{\bar c}{12}m(m^2-1)\delta_{m+n,0},
$$

and

$$
[L_m,\bar L_n]=0
$$

in an ordinary local 2D CFT on the plane.

A local operator has weights $(h,\bar h)$, scaling dimension and spin

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The central charges $c$ and $\bar c$ are not weights of an operator. They are properties of the whole theory.

## Definition from the stress-tensor OPE

The fastest definition of $c$ in a 2D CFT is the fourth-order pole in the $TT$ OPE:

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

Equivalently, taking the vacuum expectation value on the plane gives

$$
\langle T(z)T(w)\rangle
=\frac{c/2}{(z-w)^4}.
$$

The antiholomorphic sector has

$$
\langle \bar T(\bar z)\bar T(\bar w)\rangle
=\frac{\bar c/2}{(\bar z-\bar w)^4}.
$$

In a parity-invariant theory with no gravitational anomaly, $c=\bar c$. In a chiral theory or a boundary of a topological phase, one may have $c\ne\bar c$.

The mixed correlator

$$
\langle T(z)\bar T(\bar w)\rangle
$$

vanishes at separated points in an ordinary factorized CFT, up to contact-term subtleties.

## Definition from the Virasoro algebra

The same $c$ is the central term in

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

This formula is often the most memorable definition. It says that the quantum generators of local holomorphic conformal transformations are not represented by the Witt algebra itself, but by its central extension.

The global modes

$$
L_{-1},\quad L_0,\quad L_1
$$

are unaffected by the central term because $m(m^2-1)=0$ for $m=-1,0,1$. Thus the global conformal group is represented without central extension on the sphere, while local conformal transformations remember $c$.

## Definition from the Schwarzian derivative

Under a holomorphic coordinate change

$$
w=f(z),
$$

the stress tensor is not a primary field. In these conventions,

$$
T(z)=\left(\frac{dw}{dz}\right)^2T(w)+\frac{c}{12}\{w,z\},
$$

where the Schwarzian derivative is

$$
\{w,z\}
=
\frac{w'''(z)}{w'(z)}
-\frac{3}{2}\left(\frac{w''(z)}{w'(z)}\right)^2.
$$

The Schwarzian term vanishes for Möbius transformations,

$$
w=\frac{az+b}{cz+d},
\qquad ad-bc\ne0,
$$

which is another way to see that the central charge affects local conformal transformations but not the global conformal group.

A useful consistency check is the plane-to-cylinder map. If

$$
z=e^w,
\qquad w=\tau+i\sigma,
$$

then

$$
\{z,w\}=-\frac12.
$$

Since the plane vacuum has $\langle T(z)\rangle=0$, the cylinder has a nonzero vacuum expectation value proportional to $-c/24$ after the standard stress-tensor transformation to the cylinder.

## Cylinder vacuum energy

On a spatial circle, the Hamiltonian is proportional to

$$
L_0+\bar L_0-\frac{c+\bar c}{24}.
$$

For a cylinder of circumference $L$, the Hamiltonian is conventionally

$$
H=\frac{2\pi}{L}\left(L_0+\bar L_0-\frac{c+\bar c}{24}\right).
$$

The vacuum energy is therefore

$$
E_0=-\frac{\pi}{12L}(c+\bar c).
$$

If $c=\bar c$, this becomes

$$
E_0=-\frac{\pi c}{6L}.
$$

This is the finite-size Casimir energy of a two-dimensional CFT on a circle. It is one of the most direct physical appearances of $c$.

The momentum on the circle is

$$
P=\frac{2\pi}{L}\left(L_0-\bar L_0-\frac{c-\bar c}{24}\right),
$$

up to convention-dependent choices of orientation. When $c-\bar c\ne0$, the theory has a chiral gravitational anomaly, and one must be careful about modular invariance and orientation-reversing symmetries.

## Trace anomaly on curved backgrounds

In flat space at separated points, a CFT has a traceless stress tensor. On a curved two-dimensional background, the quantum theory generally has a trace anomaly. In common Euclidean conventions,

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{c}{12}R
$$

for a single holomorphic-plus-antiholomorphic nonchiral CFT convention where $T(z)$ is normalized without explicit $2\pi$ factors. In geometric-QFT conventions one often instead writes

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{c}{24\pi}R.
$$

The difference is not physics; it is normalization of the stress tensor and the metric variation. Whenever comparing sources, check whether their stress tensor is the CFT-normalized $T(z)$ or the metric-normalized $T_{\mu\nu}$.

The key point is invariant:

$$
\text{the coefficient of the two-dimensional Weyl anomaly is the central charge.}
$$

This is why $c$ is sometimes described as counting degrees of freedom. That statement is useful but imprecise; see below.

## Examples

Common examples include:

| Theory | Holomorphic central charge |
|---|---:|
| Real free scalar, noncompact | $c=1$ |
| Compact free boson at any radius | $c=1$ |
| Real free Majorana fermion | $c=\frac12$ |
| Complex free fermion | $c=1$ |
| $bc$ ghosts with weights $(2,-1)$ | $c=-26$ |
| Unitary minimal model labeled by $m=3,4,\ldots$ | $c=1-\frac{6}{m(m+1)}$ |
| WZW model for simple $\mathfrak g$ at level $k$ | $c=\frac{k\dim\mathfrak g}{k+h^\vee}$ |

A product theory has additive central charge:

$$
c_{A\times B}=c_A+c_B,
\qquad
\bar c_{A\times B}=\bar c_A+\bar c_B.
$$

This follows because the total stress tensor is the sum

$$
T_{A\times B}=T_A+T_B,
$$

and the two factors have nonsingular mixed OPEs.

## Does central charge count degrees of freedom?

Roughly, yes in unitary 2D CFTs, but with caveats.

Free examples suggest that $c$ counts massless degrees of freedom:

$$
\text{real scalar}: c=1,
\qquad
\text{real Majorana fermion}: c=\frac12.
$$

The Cardy formula also shows that $c$ controls the asymptotic density of states. For a unitary modular-invariant CFT with suitable discreteness assumptions, the high-energy density of states grows as

$$
\rho(\Delta)\sim
\exp\left(2\pi\sqrt{\frac{c_{\mathrm{eff}}\Delta}{6}}+2\pi\sqrt{\frac{\bar c_{\mathrm{eff}}\bar\Delta}{6}}\right),
$$

where the effective central charge accounts for the lowest weights in nonvacuum or nonunitary situations.

However, $c$ is not literally a count of fields. Interacting CFTs, constrained systems, ghosts, nonunitary theories, logarithmic CFTs, and topological sectors can violate the naive counting intuition. The precise statement is that $c$ is the coefficient of the stress-tensor anomaly and Virasoro central extension.

## Central charge and RG flow

In unitary, Lorentz-invariant, local two-dimensional QFTs satisfying the usual assumptions, Zamolodchikov's $c$-theorem says that there exists a function $C$ along RG flows such that

$$
C_{\mathrm{UV}}>C_{\mathrm{IR}}
$$

for a nontrivial flow between fixed points, and at fixed points

$$
C=c.
$$

This is one of the sharpest statements behind the intuition that the number of degrees of freedom decreases along RG flow.

Do not overgeneralize it. Higher dimensions have different monotonic quantities, such as the $F$ quantity in three dimensions and the $a$ anomaly in four dimensions. Nonunitary flows, boundary flows, defect flows, and logarithmic theories require separate care.

## Central charge versus current levels

The central charge is associated with spacetime conformal symmetry. A current algebra has its own central term, usually called a **level**. For a holomorphic current $J^a(z)$,

$$
J^a(z)J^b(w)
\sim
\frac{k\delta^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_c J^c(w)}{z-w}.
$$

The number $k$ is not the same as $c$. In WZW models they are related by the Sugawara construction,

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee},
$$

but the distinction matters. A theory can have a Virasoro central charge and many current-algebra levels.

## Central charge and modular invariance

On the torus, central charge enters through characters. A holomorphic Virasoro character has the schematic form

$$
\chi_h(q)=\operatorname{Tr}_{\mathcal V_h}q^{L_0-c/24}.
$$

The shift by $c/24$ is the same cylinder vacuum-energy shift. Modular transformations mix characters and strongly constrain the allowed spectra.

This is one reason $c$ is the first label in many classifications of 2D CFTs. For example, unitary minimal models occur at

$$
c=1-\frac{6}{m(m+1)},
\qquad m=3,4,5,\ldots.
$$

The Ising CFT is $m=3$ and has

$$
c=\frac12.
$$

## Common pitfalls

**Using $c$ before fixing the normalization of $T$.** If the stress tensor is rescaled arbitrarily, the coefficient of the $TT$ two-point function changes. In a CFT, the Ward identity fixes the physical normalization of $T$, and then $c$ is meaningful.

**Confusing $c$ with $c+\bar c$.** Thermodynamics and finite-size energy often see $c+\bar c$, while gravitational anomaly physics sees $c-\bar c$.

**Forgetting the Schwarzian.** The stress tensor is not a primary. Under a general local conformal map it picks up the Schwarzian derivative.

**Assuming $c$ is always positive.** In unitary CFTs with a normal stress tensor, $c\ge0$. Nonunitary theories and ghost systems can have negative central charge.

**Treating contact terms as separated-point data.** The central charge is fixed by the separated-point $TT$ correlator, but curved-background formulas and Ward identities can include contact terms whose convention dependence must be handled carefully.

**Calling every monotonic quantity a central charge.** In other dimensions there are anomaly coefficients and sphere free energies that play analogous roles, but they are not the 2D Virasoro central charge.

## Relations to other pages

- [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) derives the commutator containing $c$.
- [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) introduces $T(z)$ and the stress-tensor Ward identity.
- [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/) derives the $c/24$ shift from the Schwarzian.
- [Conformal Anomaly in 2D](/cft-bootstrap/virasoro-central-charge/conformal-anomaly-in-2d/) develops the curved-background Weyl-anomaly perspective.
- [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) explains why special central charges below $1$ support finite operator content.
- [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/) uses $q^{L_0-c/24}$ to organize spectra.
- [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) uses central charge and modular invariance to constrain spectra.
- [Holographic CFT](/cft-bootstrap/holographic-cft/) treats large-$c$ limits, semiclassical Virasoro blocks, and Brown–Henneaux-type relations.

## Research status

The equivalence between the $TT$ OPE coefficient, the Virasoro central extension, the Schwarzian transformation law, the cylinder Casimir energy, and the two-dimensional Weyl anomaly is standard.

Active research uses central charge in more elaborate settings: modular bootstrap at large and small $c$, logarithmic and nonsemisimple CFT, chiral phases with $c\ne\bar c$, holographic CFT at large $c$, irrational CFT, defect and boundary central charges, and categorical formulations of rational CFT.

## Exercises

### Exercise 1: Central term from the two-point function

Assume

$$
T(z)T(w)\sim \frac{A}{(z-w)^4}+\frac{2T(w)}{(z-w)^2}+\frac{\partial T(w)}{z-w}.
$$

Show that the Virasoro central term is

$$
\frac{A}{6}m(m^2-1)\delta_{m+n,0}.
$$

Then identify $A$ in terms of $c$.

<details><summary><strong>Solution</strong></summary>

The fourth-order pole contributes

$$
A\oint_0\frac{dw}{2\pi i}\,w^{n+1}
\oint_w\frac{dz}{2\pi i}\,\frac{z^{m+1}}{(z-w)^4}.
$$

Cauchy's formula gives

$$
\oint_w\frac{dz}{2\pi i}\,\frac{z^{m+1}}{(z-w)^4}
=\frac{1}{6}(m+1)m(m-1)w^{m-2}.
$$

The remaining contour is

$$
\oint_0\frac{dw}{2\pi i}\,w^{m+n-1}=\delta_{m+n,0}.
$$

Thus the central term is

$$
\frac{A}{6}m(m^2-1)\delta_{m+n,0}.
$$

Comparing with the Virasoro convention

$$
\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

we find

$$
A=\frac{c}{2}.
$$

</details>

### Exercise 2: Schwarzian derivative of the exponential map

For

$$
z=e^w,
$$

compute $\{z,w\}$.

<details><summary><strong>Solution</strong></summary>

We have

$$
z'=e^w,
\qquad
z''=e^w,
\qquad
z'''=e^w.
$$

Therefore

$$
\{z,w\}
=\frac{z'''}{z'}-\frac32\left(\frac{z''}{z'}\right)^2
=1-\frac32
=-\frac12.
$$

This is the source of the cylinder shift proportional to $-c/24$.

</details>

### Exercise 3: Product central charge

Let two decoupled CFTs have stress tensors $T_A$ and $T_B$, with central charges $c_A$ and $c_B$. If

$$
T=T_A+T_B,
$$

show that the product theory has

$$
c=c_A+c_B.
$$

<details><summary><strong>Solution</strong></summary>

Since the two theories are decoupled, the mixed OPEs $T_A(z)T_B(w)$ and $T_B(z)T_A(w)$ are nonsingular at separated points. Thus

$$
T(z)T(w)=T_A(z)T_A(w)+T_B(z)T_B(w)+\text{nonsingular mixed terms}.
$$

The fourth-order pole is therefore

$$
\frac{c_A/2}{(z-w)^4}+\frac{c_B/2}{(z-w)^4}
=\frac{(c_A+c_B)/2}{(z-w)^4}.
$$

So the product central charge is

$$
c=c_A+c_B.
$$

</details>

### Exercise 4: Cylinder vacuum energy

A nonchiral CFT has $c=\bar c$. Use

$$
H=\frac{2\pi}{L}\left(L_0+\bar L_0-\frac{c+\bar c}{24}\right)
$$

to find the vacuum energy on a circle of circumference $L$.

<details><summary><strong>Solution</strong></summary>

For the plane vacuum, the corresponding cylinder state has

$$
L_0=\bar L_0=0.
$$

Thus

$$
E_0
=\frac{2\pi}{L}\left(-\frac{c+\bar c}{24}\right).
$$

If $c=\bar c$,

$$
E_0=-\frac{2\pi}{L}\frac{2c}{24}
=-\frac{\pi c}{6L}.
$$

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- J. Cardy, “Conformal invariance and universality in finite-size scaling,” *Journal of Physics A* **17** (1984).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- A. B. Zamolodchikov, “Irreversibility of the flux of the renormalization group in a 2D field theory,” *JETP Letters* **43** (1986).
- H. W. J. Blöte, J. L. Cardy, and M. P. Nightingale, “Conformal invariance, the central charge, and universal finite-size amplitudes at criticality,” *Physical Review Letters* **56** (1986).
- I. Affleck, “Universal term in the free energy at a critical point and the conformal anomaly,” *Physical Review Letters* **56** (1986).

## Version history

- 2026-06-28: First polished draft. Fixes central-charge conventions and connects the $TT$ OPE, Virasoro algebra, Schwarzian derivative, cylinder energy, and trace anomaly.
