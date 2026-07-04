---
title: "Free Fields in 2D CFT"
description: "Free bosons, compact bosons, free fermions, bc ghosts, vertex operators, central charge, and their role in string worldsheets."
sidebar:
  order: 4
---

## Goal

Free fields are the laboratory where the abstract language of two-dimensional CFT becomes concrete. They let us compute OPEs, stress tensors, central charges, vertex-operator dimensions, Hilbert spaces, characters, and partition functions with almost no black box. They are also the first CFTs one meets in string theory: spacetime coordinates on the worldsheet are free bosons in flat space, worldsheet fermions appear in superstrings, and ghost systems appear after gauge fixing worldsheet diffeomorphism and Weyl symmetry.

This page introduces the three basic free-field families that every AdS/CFT student should know:

$$
\text{free bosons},
\qquad
\text{free fermions},
\qquad
bc\text{ ghost systems}.
$$

The emphasis is not on solving every free model in maximal detail. The goal is to build a reliable toolkit: OPE normalization, stress tensors, central charge, vertex operators, compactification, and the precise way these objects prepare us for worldsheet string theory and AdS/CFT.

## Conventions

We work locally on the Euclidean complex plane with coordinates $z,\bar z$. The singular part of an OPE is denoted by $\sim$. Regular terms are usually omitted. Holomorphic and antiholomorphic sectors are treated independently unless stated otherwise.

For a holomorphic stress tensor, the defining OPE with a primary field $\phi$ of weight $h$ is

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w}.
$$

The stress-tensor OPE is

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

Here $c$ is the holomorphic central charge. A full nonchiral CFT also has an antiholomorphic central charge $\bar c$.

One small warning: the symbol $c$ is unfortunately overloaded. In this page it can denote either the central charge or the ghost field $c(z)$. When confusion is likely, I write $c_{\rm Vir}$ for the central charge.

## Why free fields matter

Free fields are special because all correlators reduce to two-point contractions. This is Wick's theorem in CFT clothing. For example, once the singular OPE

$$
A(z)B(w)\sim \frac{1}{z-w}
$$

is known, the singular parts of composite-operator OPEs can be computed by normal ordering and contractions. In practice, this means that free CFTs are exactly solvable.

But free fields are not merely simple examples. They play four structural roles.

First, they are local building blocks of many rational and nonrational CFTs. The Ising CFT can be described by a free Majorana fermion. Many current algebras have free-field realizations. The Coulomb-gas construction of minimal models uses a free boson with background charge.

Second, they are the basic worldsheet fields of perturbative string theory. In flat space, the bosonic string has $D$ free bosons $X^\mu$. The RNS superstring adds worldsheet fermions $\psi^\mu$. Gauge fixing introduces ghost systems.

Third, compact free bosons explain momentum, winding, T-duality, and vertex operators. These are not optional decorations; they are the first exact example of how target-space geometry is encoded by a worldsheet CFT.

Fourth, free fields teach what is and is not universal. A free scalar in two dimensions has logarithmic two-point function, so the field $X$ itself is not quite an ordinary primary local operator. Its derivative $\partial X$ is a clean primary, and exponentials of $X$ are the physical vertex operators.

## The free boson

The free real boson $X(z,\bar z)$ is governed by the Gaussian action

$$
S_X
=
\frac{1}{4\pi\alpha'}
\int d^2z\,\partial X\bar\partial X.
$$

The equation of motion is

$$
\partial\bar\partial X=0,
$$

so locally

$$
X(z,\bar z)=X_L(z)+X_R(\bar z).
$$

The basic OPE is

$$
X(z,\bar z)X(w,\bar w)
\sim
-\frac{\alpha'}{2}\log |z-w|^2.
$$

Equivalently, for the holomorphic part,

$$
X_L(z)X_L(w)
\sim
-\frac{\alpha'}{2}\log(z-w).
$$

Differentiating removes the logarithm:

$$
\partial X(z)\partial X(w)
\sim
-\frac{\alpha'}{2}\frac{1}{(z-w)^2}.
$$

The holomorphic stress tensor is

$$
T(z)
=
-\frac{1}{\alpha'}:\partial X\partial X:(z).
$$

With this normalization,

$$
T(z)T(w)
\sim
\frac{1/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

Thus one real free boson has

$$
c=1.
$$

For $D$ independent free bosons $X^\mu$ with flat target metric $\eta_{\mu\nu}$,

$$
T(z)
=
-\frac{1}{\alpha'}:\eta_{\mu\nu}\partial X^\mu\partial X^\nu:(z),
\qquad
c=D.
$$

This simple formula is the beginning of the central-charge calculation of critical string theory.

## The current $\partial X$

The field $X$ has a logarithmic OPE, so it is not an ordinary local primary in the same sense as a power-law operator. The derivative

$$
J(z)=i\partial X(z)
$$

is much better behaved. It is a holomorphic current of weight $1$:

$$
T(z)J(w)
\sim
\frac{J(w)}{(z-w)^2}
+
\frac{\partial J(w)}{z-w}.
$$

The current OPE is

$$
J(z)J(w)
\sim
\frac{\alpha'}{2}\frac{1}{(z-w)^2},
$$

up to the normalization chosen for $J$. If we rescale the boson so that $X_L(z)X_L(w)\sim-\log(z-w)$, then $J=i\partial X$ obeys the canonical current algebra

$$
J(z)J(w)\sim \frac{1}{(z-w)^2}.
$$

This is the simplest example of a $U(1)$ current algebra.

## Vertex operators

The most important local operators of the free boson are exponentials. For the noncompact boson, a standard vertex operator is

$$
V_k(z,\bar z)=:e^{ikX(z,\bar z)}:.
$$

For a more general left-right decomposition, define

$$
V_{p_L,p_R}(z,\bar z)
=
:e^{ip_LX_L(z)+ip_RX_R(\bar z)}:.
$$

Using Wick contractions, one finds

$$
T(z)V_{p_L,p_R}(w,\bar w)
\sim
\frac{hV_{p_L,p_R}(w,\bar w)}{(z-w)^2}
+
\frac{\partial V_{p_L,p_R}(w,\bar w)}{z-w},
$$

with

$$
h=\frac{\alpha' p_L^2}{4},
\qquad
\bar h=\frac{\alpha' p_R^2}{4}.
$$

For a noncompact scalar with $p_L=p_R=k$,

$$
h=\bar h=\frac{\alpha' k^2}{4},
\qquad
\Delta=h+\bar h=\frac{\alpha' k^2}{2}.
$$

In string theory, the operator $:e^{ik\cdot X}:$ creates a target-space momentum eigenstate. Oscillator insertions such as $\partial X^\mu\bar\partial X^\nu e^{ik\cdot X}$ create excited string states. The physical-state conditions are then conformal-weight conditions.

## Compact boson and winding

Now impose the target-space identification

$$
X\sim X+2\pi R.
$$

The boson is compact. On a closed worldsheet spatial circle, a field configuration may wind around the target circle:

$$
X(\sigma+2\pi)=X(\sigma)+2\pi wR,
\qquad
w\in\mathbb Z.
$$

Momentum along the target circle is quantized:

$$
p=\frac{n}{R},
\qquad
n\in\mathbb Z.
$$

The left- and right-moving momenta are

$$
p_L=\frac{n}{R}+\frac{wR}{\alpha'},
\qquad
p_R=\frac{n}{R}-\frac{wR}{\alpha'}.
$$

The corresponding vertex operators have weights

$$
h=\frac{\alpha'p_L^2}{4}+N,
\qquad
\bar h=\frac{\alpha'p_R^2}{4}+\bar N,
$$

where $N$ and $\bar N$ are oscillator levels.

<figure class="doc-figure" style="--figure-width: 39rem; --caption-width: 55rem;">

![Compact boson zero modes and CFT quantum numbers](/figures/cft/free-fields-compact-boson.svg)

<figcaption>

A compact boson has both quantized momentum $n$ and winding $w$. These combine into left- and right-moving momenta $p_L,p_R$, which determine the conformal weights of vertex operators. T-duality exchanges $n$ and $w$ while flipping the sign of $p_R$.

</figcaption>
</figure>

The compact boson is the cleanest worldsheet example of target-space geometry. The radius $R$ is a CFT modulus. Changing $R$ changes the spectrum continuously, but it preserves conformal invariance.

The spectrum is invariant under T-duality:

$$
R\longleftrightarrow \frac{\alpha'}{R},
\qquad
n\longleftrightarrow w.
$$

Under this transformation,

$$
p_L\longrightarrow p_L,
\qquad
p_R\longrightarrow -p_R,
$$

so $h$ and $\bar h$ are unchanged. The sign flip of $p_R$ is invisible in the weights but important in operator identifications and target-space interpretation.

The spin of a compact-boson state is

$$
h-\bar h
=
N-\bar N+nw.
$$

For a local bosonic operator, this must be an integer. For closed-string physical states, one further imposes level matching.

## Free Majorana fermion

A chiral real, or Majorana, fermion $\psi(z)$ has OPE

$$
\psi(z)\psi(w)\sim \frac{1}{z-w}.
$$

Its stress tensor is

$$
T(z)=-\frac12:\psi\partial\psi:(z).
$$

Then

$$
T(z)\psi(w)
\sim
\frac{\frac12\psi(w)}{(z-w)^2}
+
\frac{\partial\psi(w)}{z-w},
$$

so

$$
h_\psi=\frac12.
$$

The stress-tensor OPE gives

$$
c=\frac12.
$$

This is the holomorphic half of the critical Ising CFT. The full Ising model has three primary families:

$$
\mathbf 1,
\qquad
\psi,
\qquad
\sigma,
$$

with holomorphic weights

$$
h_{\mathbf 1}=0,
\qquad
h_\psi=\frac12,
\qquad
h_\sigma=\frac{1}{16}.
$$

The spin field $\sigma$ changes fermion boundary conditions. This already hints at a major theme: even a free fermion has sectors that are not visible if one only looks at the field $\psi$ itself.

## Fermion modes: NS and R sectors

On the plane, expand

$$
\psi(z)=\sum_r \psi_r z^{-r-1/2}.
$$

The OPE gives the anticommutation relations

$$
\{\psi_r,\psi_s\}=\delta_{r+s,0}.
$$

There are two standard choices of moding:

$$
r\in\mathbb Z+\frac12
\qquad
\text{Neveu--Schwarz sector},
$$

and

$$
r\in\mathbb Z
\qquad
\text{Ramond sector}.
$$

The NS sector corresponds to antiperiodic fermions around the spatial circle. The R sector corresponds to periodic fermions and contains zero modes. These sectors are indispensable in superstring theory, where consistency requires careful sums over spin structures.

For a complex fermion, made from two real fermions,

$$
\psi(z)\psi^\dagger(w)\sim \frac{1}{z-w},
\qquad
c=1.
$$

A complex fermion may be bosonized. With a canonically normalized chiral boson $H(z)$,

$$
\psi(z)\sim :e^{iH(z)}:,
\qquad
\psi^\dagger(z)\sim :e^{-iH(z)}:,
\qquad
:\psi^\dagger\psi:(z)\sim i\partial H(z).
$$

Bosonization is one of the most useful equivalences in two-dimensional CFT. It converts fermionic boundary-condition questions into compact-boson momentum-lattice questions.

## The $bc$ ghost system

Ghost systems are free CFTs with unusual statistics and often nonunitary Hilbert spaces. They arise when gauge symmetries are fixed. In string theory, the most important example is the anticommuting $bc$ system from gauge fixing worldsheet diffeomorphisms.

Let $b(z)$ and $c(z)$ be anticommuting holomorphic fields with OPE

$$
b(z)c(w)\sim \frac{1}{z-w},
\qquad
c(z)b(w)\sim \frac{1}{z-w}.
$$

Assign conformal weights

$$
h_b=\lambda,
\qquad
h_c=1-\lambda.
$$

The stress tensor is

$$
T(z)
=
(1-\lambda):(\partial b)c:(z)
-
\lambda:b\partial c:(z).
$$

It gives

$$
T(z)b(w)
\sim
\frac{\lambda b(w)}{(z-w)^2}
+
\frac{\partial b(w)}{z-w},
$$

and

$$
T(z)c(w)
\sim
\frac{(1-\lambda)c(w)}{(z-w)^2}
+
\frac{\partial c(w)}{z-w}.
$$

The central charge is

$$
c_{bc}=1-3(2\lambda-1)^2.
$$

For the reparametrization ghosts of the bosonic string,

$$
\lambda=2,
\qquad
h_b=2,
\qquad
h_c=-1,
$$

so

$$
c_{bc}=1-3(3)^2=-26.
$$

The matter fields of the bosonic string are $D$ free bosons with $c=D$. Vanishing of the total worldsheet conformal anomaly requires

$$
c_{\rm matter}+c_{bc}=0,
$$

hence

$$
D-26=0.
$$

This is the worldsheet CFT derivation of the critical dimension of the bosonic string.

## Central charge bookkeeping

For tensor products of independent CFTs, stress tensors and central charges add:

$$
T_{\rm total}=T_1+T_2+\cdots,
\qquad
c_{\rm total}=c_1+c_2+\cdots.
$$

Some useful entries are

$$
\begin{array}{c|c}
\text{holomorphic system} & c \\
\hline
\text{one real free boson} & 1 \\
\text{one real Majorana fermion} & \frac12 \\
\text{one complex fermion} & 1 \\
\text{anticommuting }bc\text{ system with }h_b=\lambda & 1-3(2\lambda-1)^2
\end{array}
$$

Central charge is not just a number attached to $T(z)T(w)$. In two-dimensional CFT it controls finite-size energy shifts, modular behavior, Cardy growth of states, and in AdS$_3$/CFT$_2$ the Brown--Henneaux relation between boundary central charge and bulk Newton constant.

## Free fields versus generalized free fields

The phrase “free field” can mean two rather different things.

A **local free field** is a field with a Gaussian action and local OPEs. This is what we studied here: $X$, $\psi$, and $bc$ systems.

A **generalized free field** is an operator whose correlators factorize like Wick contractions but which need not arise from a local equation of motion in the boundary spacetime. Generalized free fields are central in large-$N$ CFT and holography, where they describe the leading large-$N$ behavior of single-particle bulk fields.

These two notions are related in spirit but should not be conflated. Worldsheet free bosons are local two-dimensional CFT fields. Large-$N$ generalized free operators are boundary CFT operators whose factorization reflects weakly coupled bulk physics.

## AdS/CFT checkpoint

Free fields prepare for AdS/CFT in two complementary ways.

On the **worldsheet side**, perturbative strings are described by two-dimensional CFTs. Flat-space strings are built from free bosons, worldsheet fermions, and ghosts. Strings on curved AdS backgrounds are usually interacting sigma models, but the basic constraints, central-charge bookkeeping, vertex-operator logic, and BRST structure are inherited from free-field CFT.

On the **spacetime CFT side**, free fields are not usually the final holographic answer. A holographic CFT at large $N$ is strongly constrained by sparse spectra, large-$N$ factorization, and stress-tensor dynamics. Still, free-field examples teach the language of operator dimensions, OPEs, conserved currents, and conformal blocks in a setting where every formula can be checked by hand.

The compact boson is especially important because it gives the simplest exact model of target-space geometry encoded in CFT data:

$$
R
\quad\longleftrightarrow\quad
\text{spectrum of }(h,\bar h)\text{ and OPE phases}.
$$

This is the baby version of the holographic idea that geometry is not an extra structure placed on top of a CFT; it is encoded in the CFT itself.

## Exercises

### Exercise 1 — Dimension of a free-boson vertex operator

Using

$$
X_L(z)X_L(w)\sim -\frac{\alpha'}{2}\log(z-w),
\qquad
T(z)=-\frac{1}{\alpha'}:\partial X_L\partial X_L:(z),
$$

show that

$$
V_p(w)=:e^{ipX_L(w)}:
$$

has holomorphic weight

$$
h=\frac{\alpha'p^2}{4}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the boson OPE:

$$
\partial X_L(z)X_L(w)
\sim
-\frac{\alpha'}{2}\frac{1}{z-w}.
$$

Therefore

$$
\partial X_L(z)V_p(w)
\sim
-\frac{i\alpha'p}{2}\frac{1}{z-w}V_p(w).
$$

In $T(z)V_p(w)$, the double contraction gives the second-order pole:

$$
-\frac{1}{\alpha'}
\left(-\frac{i\alpha'p}{2}\right)^2
\frac{1}{(z-w)^2}V_p(w)
=
\frac{\alpha'p^2}{4}\frac{V_p(w)}{(z-w)^2}.
$$

The single contractions give the first-order pole

$$
\frac{\partial V_p(w)}{z-w}.
$$

Thus

$$
T(z)V_p(w)
\sim
\frac{\frac{\alpha'p^2}{4}V_p(w)}{(z-w)^2}
+
\frac{\partial V_p(w)}{z-w},
$$

so

$$
h=\frac{\alpha'p^2}{4}.
$$

</details>

### Exercise 2 — Compact-boson T-duality

For the compact boson, use

$$
p_L=\frac{n}{R}+\frac{wR}{\alpha'},
\qquad
p_R=\frac{n}{R}-\frac{wR}{\alpha'}.
$$

Show that the transformation

$$
R\to \frac{\alpha'}{R},
\qquad
n\leftrightarrow w
$$

leaves $h$ and $\bar h$ invariant.

<details><summary><strong>Solution</strong></summary>

After the transformation,

$$
R'=\frac{\alpha'}{R},
\qquad
n'=w,
\qquad
w'=n.
$$

Then

$$
p_L'
=
\frac{n'}{R'}+\frac{w'R'}{\alpha'}
=
\frac{w}{\alpha'/R}+\frac{n(\alpha'/R)}{\alpha'}
=
\frac{wR}{\alpha'}+\frac{n}{R}
=
p_L.
$$

Similarly,

$$
p_R'
=
\frac{wR}{\alpha'}-\frac{n}{R}
=
-p_R.
$$

Therefore

$$
p_L'^2=p_L^2,
\qquad
p_R'^2=p_R^2.
$$

Since

$$
h=\frac{\alpha'p_L^2}{4}+N,
\qquad
\bar h=\frac{\alpha'p_R^2}{4}+\bar N,
$$

both weights are invariant, assuming the oscillator levels are mapped trivially.

</details>

### Exercise 3 — The central charge of the bosonic string

A bosonic string in flat $D$-dimensional spacetime has $D$ free worldsheet bosons and a reparametrization ghost system with $\lambda=2$. Show that cancellation of the total central charge gives $D=26$.

<details><summary><strong>Solution</strong></summary>

Each real free boson contributes

$$
c=1.
$$

Thus the matter central charge is

$$
c_{\rm matter}=D.
$$

For an anticommuting $bc$ system with $h_b=\lambda$, the central charge is

$$
c_{bc}=1-3(2\lambda-1)^2.
$$

For reparametrization ghosts, $\lambda=2$, so

$$
c_{bc}=1-3(4-1)^2=1-27=-26.
$$

The total central charge is

$$
c_{\rm total}=D-26.
$$

Conformal-anomaly cancellation requires

$$
c_{\rm total}=0,
$$

so

$$
D=26.
$$

</details>

### Exercise 4 — Fermion weight from the stress tensor

Given

$$
\psi(z)\psi(w)\sim \frac{1}{z-w},
\qquad
T(z)=-\frac12:\psi\partial\psi:(z),
$$

show that $\psi$ has holomorphic weight $h=1/2$.

<details><summary><strong>Solution</strong></summary>

The singular terms in $T(z)\psi(w)$ come from contracting either $\psi(z)$ or $\partial\psi(z)$ with $\psi(w)$:

$$
\psi(z)\psi(w)\sim \frac{1}{z-w},
\qquad
\partial\psi(z)\psi(w)\sim -\frac{1}{(z-w)^2}.
$$

Keeping the fermionic signs from normal ordering, one obtains

$$
T(z)\psi(w)
\sim
\frac{1}{2}\frac{\psi(w)}{(z-w)^2}
+
\frac{\partial\psi(w)}{z-w}.
$$

Comparing with the primary-field OPE,

$$
T(z)\phi(w)
\sim
\frac{h\phi(w)}{(z-w)^2}
+
\frac{\partial\phi(w)}{z-w},
$$

we read off

$$
h_\psi=\frac12.
$$

</details>

## Further reading

For a detailed classic treatment, see Di Francesco, Mathieu, and Sénéchal, especially the sections on free fields, radial quantization, the free boson, the free fermion, and ghost systems. For the string-theory use of these CFTs, compare with standard worldsheet treatments of the bosonic string and RNS superstring.
