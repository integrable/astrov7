---
title: "Critical Phenomena as CFTs"
description: "How continuous phase transitions become conformal field theories: correlation length, order parameters, critical exponents, scaling dimensions, and universality."
sidebar:
  order: 3
---

## Goal

The previous two pages built the Wilsonian and stress-tensor pictures of RG flow. We now put those ideas to work in the most concrete laboratory for CFT: continuous phase transitions.

A critical point is a place where a many-body system forgets most microscopic details. The lattice spacing $a$, the precise form of the short-distance Hamiltonian, and many irrelevant couplings become invisible at long distances. What remains is a continuum fixed point described by a CFT.

The slogan of this page is:

$$
\boxed{
\text{continuous critical point}
\quad\Longleftrightarrow\quad
\text{RG fixed point}
\quad\Longleftrightarrow\quad
\text{CFT, in favorable local unitary systems}.
}
$$

This is not merely a condensed-matter fact. It is the reason CFT is a universal language across statistical mechanics, quantum field theory, string theory, and AdS/CFT. A critical point is where correlation functions become scale-free. AdS/CFT then asks a sharper question: what kind of quantum gravity in AdS is encoded by such scale-free boundary data?

## Continuous phase transitions

A statistical system has microscopic degrees of freedom, a Hamiltonian or energy functional $H$, and a partition function

$$
Z=\sum_{\text{states}} e^{-\beta H}.
$$

A phase transition occurs when thermodynamic quantities become nonanalytic in the thermodynamic limit. The thermodynamic limit is essential: for finitely many degrees of freedom, $Z$ is usually an analytic function of the parameters.

There are two broad classes.

A **first-order transition** has a discontinuity in a first derivative of the free energy. For example, the energy or density jumps. The correlation length remains finite. There is no universal continuum CFT associated with a generic first-order transition, because the system does not develop fluctuations on arbitrarily large length scales.

A **continuous transition** has no latent heat, but higher derivatives of the free energy can diverge. More importantly, the correlation length diverges:

$$
\xi\to \infty.
$$

This divergence is the physical reason a continuum field theory emerges. Near the critical point, there is a hierarchy

$$
a\ll r\ll \xi,
$$

where $a$ is the microscopic spacing, $r$ is the distance being probed, and $\xi$ is the correlation length. In this intermediate scaling window, the system is insensitive to both the UV lattice and the IR mass scale.

At the exact critical point,

$$
\frac{\xi}{a}=\infty,
$$

and the scaling window extends to all macroscopic distances. That is the continuum limit.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![Critical phenomena as the CFT limit of a scaling window](/figures/cft/critical-phenomena-cft-limit.svg)

<figcaption>

A continuous critical point has relevant deformations such as the reduced temperature $t$ and magnetic field $h$. At the fixed point, the scaling window $a\ll r\ll \xi$ becomes infinite as $\xi/a\to\infty$, and correlation functions become power laws $G(r)\sim r^{-2\Delta}$. Away from the fixed point, the large-distance behavior is instead massive, schematically $G_c(r)\sim e^{-r/\xi}$.

</figcaption>
</figure>

## The Ising model as the prototype

The simplest useful example is the Ising model. On a $d$-dimensional lattice, each site carries a spin

$$
s_i=\pm 1.
$$

A standard Hamiltonian is

$$
H=-J\sum_{\langle ij\rangle}s_i s_j-h\sum_i s_i,
$$

where $J>0$ favors aligned neighboring spins, and $h$ is an external magnetic field. The model has a $\mathbb Z_2$ spin-flip symmetry

$$
s_i\mapsto -s_i
$$

when $h=0$.

The order parameter is the magnetization

$$
M=\langle s_i\rangle.
$$

For $T>T_c$, the system is disordered and $M=0$. For $T<T_c$, the $\mathbb Z_2$ symmetry is spontaneously broken and $M\neq0$ in infinite volume. At $T=T_c$, long-range fluctuations appear at all scales. The critical point is described by the Ising CFT.

The microscopic lattice spin becomes a continuum local operator, traditionally called $\sigma(x)$:

$$
s_i\quad\longrightarrow\quad a^{\Delta_\sigma}\sigma(x).
$$

The energy-density deformation becomes another operator, usually called $\epsilon(x)$:

$$
\sum_{\langle ij\rangle}s_i s_j
\quad\longrightarrow\quad
\int d^d x\,\epsilon(x).
$$

Near the critical point, the continuum description takes the schematic form

$$
S
=
S_{\rm Ising\ CFT}
+t\int d^d x\,\epsilon(x)
+h\int d^d x\,\sigma(x)
+\cdots,
$$

where

$$
t=\frac{T-T_c}{T_c}
$$

is the reduced temperature. The dots are irrelevant deformations. They matter microscopically, but not for the universal long-distance theory.

This equation is one of the most important bridges in the course. It says that a critical phenomenon is a CFT plus relevant perturbations.

## Correlation length

The connected two-point function of the order parameter is

$$
G_c(r)
=
\langle s_i s_j\rangle-\langle s_i\rangle\langle s_j\rangle,
\qquad
r=|i-j|a.
$$

Away from the critical point, it decays exponentially at large distance:

$$
G_c(r)\sim e^{-r/\xi}
$$

up to power-law prefactors. The length $\xi$ is the correlation length. It tells us how far one spin fluctuation can influence another.

Near the critical point,

$$
\xi\sim |t|^{-\nu}.
$$

The exponent $\nu$ is one of the basic critical exponents.

At the critical point, there is no finite correlation length. The exponential decay is replaced by a power law:

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

In CFT language, the same statement is

$$
\langle \sigma(x)\sigma(0)\rangle
=
\frac{C_\sigma}{|x|^{2\Delta_\sigma}}.
$$

Therefore

$$
\boxed{
2\Delta_\sigma=d-2+\eta.
}
$$

This is the first clean dictionary between critical exponents and CFT data. The exponent $\eta$ is not fundamental from the CFT point of view. The scaling dimension $\Delta_\sigma$ is fundamental.

## Critical exponents

The standard critical exponents describe how observables behave near $t=0$ and $h=0$. The most common definitions are

$$
\xi\sim |t|^{-\nu},
$$

$$
M\sim (-t)^\beta
\qquad
(t<0,\ h=0),
$$

$$
\chi=\frac{\partial M}{\partial h}\bigg|_{h=0}
\sim |t|^{-\gamma},
$$

$$
M\sim h^{1/\delta}
\qquad
(t=0),
$$

$$
C\sim |t|^{-\alpha},
$$

and

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}}
\qquad
(t=h=0).
$$

Here $C$ is the specific heat and $\chi$ is the susceptibility. Historically, critical phenomena were often described in terms of these exponents. CFT reorganizes the same information in a more structural way: the exponents are determined by operator dimensions and OPE data.

For the Ising universality class, the two most important relevant scalar operators are

$$
\sigma,
\qquad
\epsilon.
$$

Their dimensions are $\Delta_\sigma$ and $\Delta_\epsilon$. The corresponding coupling dimensions are

$$
y_h=d-\Delta_\sigma,
\qquad
 y_t=d-\Delta_\epsilon.
$$

The temperature deformation $t\int \epsilon$ is relevant if

$$
\Delta_\epsilon<d,
$$

and the magnetic-field deformation $h\int \sigma$ is relevant if

$$
\Delta_\sigma<d.
$$

The correlation length exponent is

$$
\boxed{
\nu=\frac{1}{d-\Delta_\epsilon}.
}
$$

The anomalous-dimension exponent is

$$
\boxed{
\eta=2\Delta_\sigma-d+2.
}
$$

Assuming hyperscaling, the other standard exponents follow from the same two CFT dimensions:

$$
\boxed{
\beta=\frac{\Delta_\sigma}{d-\Delta_\epsilon}
=\nu\Delta_\sigma,
}
$$

$$
\boxed{
\gamma=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}
=\nu(d-2\Delta_\sigma),
}
$$

$$
\boxed{
\delta=\frac{d-\Delta_\sigma}{\Delta_\sigma},
}
$$

and

$$
\boxed{
\alpha=2-d\nu.
}
$$

The word “assuming” is not decorative. Hyperscaling can fail above the upper critical dimension because dangerously irrelevant couplings can affect thermodynamics. The cleanest regime for the formulas above is below the upper critical dimension, where the interacting fixed point controls the singular free energy.

## RG derivation of scaling laws

Let $f_s(t,h)$ be the singular part of the free energy density. Near the fixed point, RG says that under a scale transformation by $b>1$,

$$
f_s(t,h)=b^{-d}f_s(b^{y_t}t,b^{y_h}h),
$$

where

$$
y_t=d-\Delta_\epsilon,
\qquad
 y_h=d-\Delta_\sigma.
$$

The correlation length scales as a length:

$$
\xi(t,h)=b\,\xi(b^{y_t}t,b^{y_h}h).
$$

Set $h=0$ and choose

$$
b=|t|^{-1/y_t}.
$$

Then

$$
\xi(t,0)=|t|^{-1/y_t}\xi(\pm1,0),
$$

so

$$
\nu=\frac1{y_t}.
$$

The same choice gives

$$
f_s(t,0)
=
|t|^{d/y_t}f_s(\pm1,0).
$$

Since $C$ is essentially two derivatives of the free energy with respect to temperature, one obtains

$$
C\sim |t|^{d/y_t-2},
$$

hence

$$
\alpha=2-\frac d{y_t}=2-d\nu.
$$

The magnetization is

$$
M=-\frac{\partial f_s}{\partial h}.
$$

Taking one $h$ derivative lowers the power by $y_h/y_t$, so

$$
M(t,0)\sim |t|^{(d-y_h)/y_t}.
$$

But $d-y_h=\Delta_\sigma$, so

$$
\beta=\frac{\Delta_\sigma}{d-\Delta_\epsilon}.
$$

Similarly, the susceptibility takes two derivatives with respect to $h$:

$$
\chi(t,0)\sim |t|^{(d-2y_h)/y_t}
=|t|^{-(2y_h-d)/y_t}.
$$

Therefore

$$
\gamma=\frac{2y_h-d}{y_t}
=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}.
$$

At $t=0$, choose instead

$$
b=|h|^{-1/y_h}.
$$

Then

$$
f_s(0,h)\sim |h|^{d/y_h},
$$

and

$$
M(0,h)\sim |h|^{d/y_h-1}.
$$

Thus

$$
\frac1\delta=\frac{d-y_h}{y_h}
=\frac{\Delta_\sigma}{d-\Delta_\sigma}.
$$

This derivation is worth mastering. It is the reason the CFT spectrum is more fundamental than the old list of thermodynamic exponents.

## Scaling functions

Critical exponents are only the first layer. The full scaling form of correlation functions is richer.

For the order parameter, RG predicts

$$
\langle \sigma(x)\sigma(0)\rangle_t
=
\frac{1}{|x|^{2\Delta_\sigma}}
F_\pm\left(\frac{|x|}{\xi}\right),
$$

where $F_+$ and $F_-$ refer to the disordered and ordered sides of the transition. At short distances compared to the correlation length,

$$
|x|\ll\xi,
$$

the function approaches a constant and the correlator looks critical. At large distances,

$$
|x|\gg\xi,
$$

the scaling function crosses over to massive behavior.

This is the conceptual point behind universality: different microscopic systems can have different short-distance definitions of $\sigma$, different lattice symmetries, and different irrelevant corrections, but they share the same scaling functions after normalization if they flow to the same fixed point.

## Universality classes

A universality class is an RG basin of attraction. Many microscopic theories can flow to the same fixed point.

The Ising universality class is characterized by a scalar order parameter with a $\mathbb Z_2$ symmetry. Examples include magnets, binary fluids, lattice gases, and many effective scalar theories. Their microscopic Hamiltonians differ, but after tuning the relevant deformations, their long-distance critical behavior is governed by the same CFT.

From the Wilsonian point of view, this happens because irrelevant operators die under coarse graining. Suppose the fixed point is perturbed as

$$
S=S_*+\sum_i \lambda_i\int d^d x\,\mathcal O_i(x).
$$

The coupling $\lambda_i$ has RG eigenvalue

$$
y_i=d-\Delta_i.
$$

If $y_i<0$, the deformation is irrelevant. Its effect at long distances is suppressed. If $y_i>0$, it is relevant and must be tuned to reach the critical point.

For the Ising CFT, $\epsilon$ and $\sigma$ are the two familiar relevant deformations. To reach the critical point, we tune both $t$ and $h$ to zero. In the usual zero-field transition, the symmetry sets $h=0$, so only temperature must be tuned.

## Exact two-dimensional Ising data

The two-dimensional Ising CFT is one of the jewels of exact CFT. Its central charge is

$$
c=\frac12,
$$

and its three primary fields are

$$
\mathbf 1,
\qquad
\sigma,
\qquad
\epsilon.
$$

Their scaling dimensions are

$$
\Delta_{\mathbf 1}=0,
\qquad
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1.
$$

For $d=2$, the formulas above give

$$
\nu=\frac{1}{2-1}=1,
$$

$$
\eta=2\cdot\frac18-2+2=\frac14,
$$

$$
\beta=\nu\Delta_\sigma=\frac18,
$$

$$
\gamma=\nu(d-2\Delta_\sigma)
=2-\frac14
=\frac74,
$$

$$
\delta=\frac{2-1/8}{1/8}=15,
$$

and

$$
\alpha=2-2\nu=0.
$$

The exponent $\alpha=0$ means the specific heat has a logarithmic singularity rather than a simple power-law divergence. This is a reminder that critical exponents are shorthand for leading singular behavior, not a substitute for the full scaling analysis.

## Three-dimensional Ising and the bootstrap viewpoint

The three-dimensional Ising CFT is not known by exact solution, but it is one of the best understood nontrivial CFTs. Numerically, it has approximately

$$
\Delta_\sigma\approx 0.518,
\qquad
\Delta_\epsilon\approx 1.413.
$$

These numbers imply

$$
\nu\approx \frac{1}{3-1.413}\approx0.63,
$$

and

$$
\eta\approx 2(0.518)-3+2\approx0.036.
$$

The modern conformal bootstrap determines these numbers not by simulating a lattice Hamiltonian directly, but by imposing consistency of the CFT operator algebra: crossing symmetry, unitarity, and the OPE. That is a major theme of this course. Critical phenomena provide the experimental and conceptual origin; the bootstrap provides the CFT-native formulation.

## Quantum critical points

A classical statistical system in $d$ Euclidean dimensions is closely related to a Euclidean QFT in $d$ dimensions. A quantum many-body system in $D$ spatial dimensions has a Lorentzian time direction. At zero temperature, a quantum critical point is described by a QFT in

$$
d=D+1
$$

spacetime dimensions, often with an emergent relativistic scaling symmetry.

If the dynamic critical exponent is $z=1$, the quantum critical theory can be a relativistic CFT. If $z\neq1$, the scaling is anisotropic:

$$
t\mapsto b^z t,
\qquad
x\mapsto b x,
$$

and the theory is not a relativistic CFT in the sense used in AdS/CFT. There are holographic models for Lifshitz and hyperscaling-violating systems, but the standard AdS/CFT correspondence is tied to relativistic conformal symmetry.

This distinction is important. Not every scale-invariant critical point is a relativistic CFT. For this course, our main target is the relativistic case, where the global conformal group is $SO(d,2)$ in Lorentzian signature.

## Finite-size scaling and the cylinder

At criticality, the only length scale in a finite system is the size $L$. Thus the singular free energy density scales as

$$
f_s(L)\sim L^{-d}.
$$

More generally, a local operator with dimension $\Delta$ has finite-size scaling

$$
\langle \mathcal O\rangle_L\sim L^{-\Delta}
$$

if no symmetry forces the one-point function to vanish.

CFT sharpens this. Put the theory on a spatial sphere or circle. Radial quantization maps flat space to the cylinder, and operator dimensions become energies:

$$
E_{\mathcal O}-E_0=\frac{\Delta_{\mathcal O}}{R}.
$$

This is the state-operator correspondence, which we will develop later. It is already visible in finite-size scaling: the spectrum of a finite critical system knows the scaling dimensions of the continuum CFT.

## The holographic checkpoint

For AdS/CFT, critical phenomena teach three habits of thought.

First, the CFT is defined by long-distance data, not by a microscopic lattice Hamiltonian. In holography, the boundary CFT is often not introduced as a lattice model at all. It is specified by its operator spectrum, correlation functions, symmetries, and large-$N$ structure.

Second, relevant deformations are sources for operators. A boundary deformation

$$
\delta S=\lambda\int d^d x\,\mathcal O(x)
$$

is holographically described by changing the boundary condition of the dual bulk field $\phi_{\mathcal O}$. For a scalar operator,

$$
m^2R_{\rm AdS}^2=\Delta(\Delta-d).
$$

Thus the same number $\Delta$ that controls critical exponents also controls the mass of a bulk field.

Third, the correlation length in a deformed CFT is the inverse mass gap:

$$
\xi\sim m_{\rm gap}^{-1}.
$$

At the fixed point, $m_{\rm gap}=0$ and the bulk geometry has exact AdS asymptotics. Away from the fixed point, relevant deformations drive RG flows, which holographically become radial flows in the bulk. The radial direction of AdS is the geometric avatar of scale.

## Common pitfalls

### Pitfall 1: thinking every phase transition gives a CFT

Only continuous critical points with diverging correlation length are candidates for CFT descriptions. A generic first-order transition has finite $\xi$ and does not produce a universal continuum fixed point.

### Pitfall 2: confusing the critical theory with a thermal state

A CFT can be placed at nonzero temperature, but the thermal state introduces the scale $\beta=1/T$. The theory remains a CFT, but the state is not invariant under dilatations. A classical statistical critical point is different: the continuum Euclidean theory itself sits at an RG fixed point.

### Pitfall 3: treating critical exponents as independent data

The exponents $\alpha,\beta,\gamma,\delta,\nu,\eta$ are not independent in a CFT. They are mostly repackaged information about operator dimensions, especially $\Delta_\sigma$ and $\Delta_\epsilon$ in the Ising universality class.

### Pitfall 4: forgetting dangerously irrelevant operators

Below the upper critical dimension, hyperscaling is usually safe. Above it, some irrelevant couplings can affect thermodynamic singularities. Then naive relations such as $\alpha=2-d\nu$ may fail even though the RG logic remains correct when refined.

## Summary

A continuous critical point is a continuum limit in which

$$
\frac{\xi}{a}\to\infty.
$$

At the fixed point, correlators become power laws:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac1{|x|^{2\Delta}}.
$$

Relevant perturbations move the theory away from criticality:

$$
S=S_*+\sum_i\lambda_i\int d^d x\,\mathcal O_i,
\qquad
 y_i=d-\Delta_i.
$$

For the Ising universality class,

$$
S=S_{\rm Ising\ CFT}
+t\int \epsilon
+h\int \sigma+\text{irrelevant terms}.
$$

The critical exponents are determined by CFT dimensions:

$$
\nu=\frac1{d-\Delta_\epsilon},
\qquad
\eta=2\Delta_\sigma-d+2,
$$

with other exponents following from scaling relations when hyperscaling applies.

This is the first major payoff of the course: CFT turns critical phenomena from a list of exponents into a theory of local operators.

## Exercises

### Exercise 1 — From $\eta$ to $\Delta_\sigma$

At a critical point, the connected order-parameter correlator behaves as

$$
G_c(r)\sim \frac1{r^{d-2+\eta}}.
$$

In a CFT, the corresponding scalar primary obeys

$$
\langle\sigma(x)\sigma(0)\rangle\sim \frac1{|x|^{2\Delta_\sigma}}.
$$

Derive the relation between $\eta$ and $\Delta_\sigma$.

<details><summary><strong>Solution</strong></summary>

Equate the powers of $r$:

$$
2\Delta_\sigma=d-2+\eta.
$$

Therefore

$$
\Delta_\sigma=\frac{d-2+\eta}{2},
\qquad
\eta=2\Delta_\sigma-d+2.
$$

</details>

### Exercise 2 — Correlation length exponent from $\Delta_\epsilon$

Suppose the temperature deformation of a CFT is

$$
\delta S=t\int d^d x\,\epsilon(x),
$$

where $\epsilon$ has scaling dimension $\Delta_\epsilon$. Show that

$$
\nu=\frac1{d-\Delta_\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

The coupling $t$ has RG eigenvalue

$$
y_t=d-\Delta_\epsilon.
$$

Under a scale transformation by $b$,

$$
t\mapsto b^{y_t}t.
$$

The correlation length obeys

$$
\xi(t)=b\,\xi(b^{y_t}t).
$$

Choose $b=|t|^{-1/y_t}$, so that $b^{y_t}t=\pm1$. Then

$$
\xi(t)=|t|^{-1/y_t}\xi(\pm1).
$$

Thus

$$
\nu=\frac1{y_t}=\frac1{d-\Delta_\epsilon}.
$$

</details>

### Exercise 3 — Magnetization and susceptibility exponents

Using the scaling form

$$
f_s(t,h)=b^{-d}f_s(b^{y_t}t,b^{y_h}h),
$$

with

$$
y_t=d-\Delta_\epsilon,
\qquad
 y_h=d-\Delta_\sigma,
$$

derive

$$
\beta=\frac{\Delta_\sigma}{d-\Delta_\epsilon},
\qquad
\gamma=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

Set $h=0$ and choose

$$
b=|t|^{-1/y_t}.
$$

Then

$$
f_s(t,0)=|t|^{d/y_t}f_s(\pm1,0).
$$

The magnetization is one derivative with respect to $h$:

$$
M=-\frac{\partial f_s}{\partial h}.
$$

One derivative with respect to $h$ contributes a factor $b^{y_h}$ before setting $b=|t|^{-1/y_t}$. Therefore

$$
M(t,0)\sim |t|^{(d-y_h)/y_t}.
$$

Since $d-y_h=\Delta_\sigma$,

$$
\beta=\frac{\Delta_\sigma}{y_t}
=\frac{\Delta_\sigma}{d-\Delta_\epsilon}.
$$

The susceptibility is two derivatives with respect to $h$:

$$
\chi=\frac{\partial M}{\partial h}
=-\frac{\partial^2 f_s}{\partial h^2}.
$$

Thus

$$
\chi(t,0)\sim |t|^{(d-2y_h)/y_t}.
$$

By definition $\chi\sim |t|^{-\gamma}$, so

$$
\gamma=\frac{2y_h-d}{y_t}.
$$

Substituting $y_h=d-\Delta_\sigma$ gives

$$
\gamma=\frac{2(d-\Delta_\sigma)-d}{d-\Delta_\epsilon}
=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}.
$$

</details>

### Exercise 4 — Exact exponents of the two-dimensional Ising model

The 2D Ising CFT has

$$
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1,
\qquad
 d=2.
$$

Compute $\nu$, $\eta$, $\beta$, $\gamma$, and $\delta$.

<details><summary><strong>Solution</strong></summary>

First,

$$
\nu=\frac1{d-\Delta_\epsilon}
=\frac1{2-1}=1.
$$

Next,

$$
\eta=2\Delta_\sigma-d+2
=2\cdot\frac18-2+2
=\frac14.
$$

The magnetization exponent is

$$
\beta=\nu\Delta_\sigma=\frac18.
$$

The susceptibility exponent is

$$
\gamma=\nu(d-2\Delta_\sigma)
=2-\frac14
=\frac74.
$$

Finally,

$$
\delta=\frac{d-\Delta_\sigma}{\Delta_\sigma}
=\frac{2-1/8}{1/8}=15.
$$

</details>

### Exercise 5 — The CFT meaning of finite-size scaling

At a critical point in a finite box of size $L$, argue that a scalar one-point function, if allowed by symmetries, scales as

$$
\langle\mathcal O\rangle_L\sim L^{-\Delta}.
$$

<details><summary><strong>Solution</strong></summary>

At the critical point there is no intrinsic correlation length. In a finite system, the only remaining macroscopic length scale is $L$.

A scalar primary of dimension $\Delta$ transforms under scaling as

$$
\mathcal O(x)\mapsto b^{\Delta}\mathcal O(bx)
$$

in the convention where correlators behave as $|x|^{-2\Delta}$. Therefore its expectation value must have units of length to the power $-\Delta$. Since $L$ is the only available scale,

$$
\langle\mathcal O\rangle_L\propto L^{-\Delta}.
$$

The proportionality constant is universal only after one fixes the normalization of $\mathcal O$ and the geometry of the finite system.

</details>

