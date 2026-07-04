---
title: "Entanglement and Modular Hamiltonian"
description: "Reduced density matrices, entanglement entropy, modular Hamiltonians, the ball-region first law, replica trick, and the RT/HRT preparation for AdS/CFT."
sidebar:
  order: 4
---

Entanglement is where CFT starts to look like geometry.

A CFT is defined by local operator data, but a state of the CFT contains nonlocal information. Given a spatial region $A$, the reduced density matrix $\rho_A$ knows how the degrees of freedom in $A$ are correlated with the degrees of freedom in the complement $\bar A$. The entropy of $\rho_A$ is not an ordinary thermodynamic entropy: even the vacuum has nonzero entanglement entropy. In holographic CFTs this entropy becomes an area in one higher-dimensional spacetime.

This page introduces the CFT side of that story. The essential chain of ideas is

$$
\boxed{
\rho_A
\quad\longrightarrow\quad
K_A=-\log\rho_A
\quad\longrightarrow\quad
\delta S_A=\delta\langle K_A\rangle
\quad\longrightarrow\quad
S_A={\mathrm{Area}(\gamma_A)\over 4G_N}+\cdots
}
$$

The central point is that entanglement entropy is usually hard, but for special regions in the vacuum of a CFT, the modular Hamiltonian is known exactly. The most important example for AdS/CFT is a ball-shaped region.

## Reduced density matrix

Let the CFT be quantized on a Cauchy slice $\Sigma$. Suppose $A\subset\Sigma$ is a spatial subregion and $\bar A$ is its complement. In a regulated theory, the Hilbert space is approximately factorized as

$$
\mathcal H_\Sigma\simeq \mathcal H_A\otimes \mathcal H_{\bar A}.
$$

This factorization is morally correct for a scalar lattice theory. In continuum QFT it is more subtle because of UV modes near the entangling surface $\partial A$, and in gauge theory there are additional subtleties associated with constraints and edge modes. For this course, the regulated picture is the right starting point.

Given a global density matrix $\rho$, the reduced density matrix on $A$ is

$$
\rho_A=\operatorname{Tr}_{\bar A}\rho,
\qquad
\operatorname{Tr}_A\rho_A=1.
$$

For a pure global state $\rho=|\Psi\rangle\langle\Psi|$, the reduced density matrix is generally mixed. The entanglement entropy of $A$ is the von Neumann entropy

$$
S_A=-\operatorname{Tr}_A\rho_A\log\rho_A.
$$

If the global state is pure and the Hilbert-space factorization is exact, then

$$
S_A=S_{\bar A}.
$$

This equality is a useful diagnostic. If the global state is thermal, mixed, or if the factorization has gauge-theory subtleties, this equality need not hold in the naive form.

The Rényi entropies are

$$
S_n(A)={1\over 1-n}\log\operatorname{Tr}\rho_A^n,
\qquad n>0,
\qquad n\neq 1.
$$

The entanglement entropy is obtained by taking the limit

$$
S_A=\lim_{n\to 1}S_n(A).
$$

The Rényi entropies contain more information than $S_A$. In principle, knowing all $\operatorname{Tr}\rho_A^n$ reconstructs the spectrum of $\rho_A$.

## UV structure of entanglement entropy

Entanglement entropy in continuum QFT is UV divergent. The reason is local: modes just inside and just outside $\partial A$ are highly entangled at arbitrarily short distances.

For a smooth entangling surface in a $d$-dimensional CFT, the leading divergence has the area-law form

$$
S_A
=
\alpha_{d-2}{\operatorname{Area}(\partial A)\over \epsilon^{d-2}}
+\text{subleading divergences}
+\text{universal part},
\qquad d>2,
$$

where $\epsilon$ is a UV cutoff. The coefficient $\alpha_{d-2}$ is regulator dependent. It is not a universal observable.

The universal part is the real prize. Its form depends on the spacetime dimension. In even $d$, there is usually a universal logarithmic term. In odd $d$, there is often a universal cutoff-independent constant term. In $d=2$, the leading term itself is logarithmic and controlled by the central charge.

For example, in a parity-invariant two-dimensional CFT with $c_L=c_R=c$, the entanglement entropy of a single interval of length $\ell$ in the vacuum on the plane is

$$
\boxed{
S_A={c\over 3}\log{\ell\over \epsilon}+s_0
}
$$

where $s_0$ is nonuniversal. More generally, if $c_L\neq c_R$, the coefficient becomes $(c_L+c_R)/6$.

This formula is one of the cleanest places where the central charge becomes a measure of degrees of freedom.

## Modular Hamiltonian

The modular Hamiltonian of region $A$ is defined by

$$
\boxed{
K_A=-\log\rho_A
}
$$

with the normalization convention $\operatorname{Tr}e^{-K_A}=1$. Equivalently,

$$
\rho_A=e^{-K_A}.
$$

Some references instead write

$$
\rho_A={e^{-\widetilde K_A}\over Z_A}.
$$

Then

$$
K_A=\widetilde K_A+\log Z_A.
$$

The two conventions differ by an additive constant. Additive constants do not affect modular flow or variations $\delta\langle K_A\rangle$, but they do affect the literal equation $S_A=\langle K_A\rangle$. With the normalized convention above,

$$
S_A=\operatorname{Tr}\rho_A K_A=\langle K_A\rangle.
$$

The modular Hamiltonian generates modular flow:

$$
\mathcal O_A(s)
=e^{isK_A}\mathcal O_A e^{-isK_A}.
$$

This looks like time evolution, but it is usually not generated by a local integral of the stress tensor. For a generic region $A$ and a generic state, $K_A$ is an extremely nonlocal operator.

That is why the few known local examples are so important.

## Vacuum half-space: Rindler modular Hamiltonian

Consider the CFT vacuum in flat Lorentzian spacetime and the half-space region

$$
A=\{x^1>0,\ t=0\}.
$$

The causal domain of $A$ is the right Rindler wedge. The modular Hamiltonian is local and equals the boost generator:

$$
\boxed{
K_A=2\pi\int_{x^1>0} d^{d-1}x\,x^1T_{00}(0,x^1,\vec x_\perp)
}
$$

up to the normalization convention discussed above.

This result is the QFT version of the statement that the Minkowski vacuum restricted to a Rindler wedge is thermal with respect to boosts. In Euclidean signature, the argument is almost geometric: the plane near the entangling surface is described by polar coordinates, and regularity requires angular period $2\pi$.

The half-space formula is the prototype for black-hole thermality. Near a smooth horizon, the geometry locally looks Rindler. This is why modular Hamiltonians, Unruh physics, and black-hole entropy are not separate subjects.

## Vacuum ball: the most important CFT example

Now take the CFT vacuum and let $A=B_R$ be the ball of radius $R$ at $t=0$:

$$
B_R=\{\vec x\in\mathbb R^{d-1}: r=|\vec x|<R\}.
$$

The domain of dependence $D(B_R)$ is a causal diamond. A conformal transformation maps this diamond to a hyperbolic cylinder,

$$
D(B_R)
\quad\longleftrightarrow\quad
\mathbb R_\tau\times H^{d-1}.
$$

Under this map, the vacuum reduced density matrix on the ball becomes a thermal density matrix on hyperbolic space. The modular flow is generated by the conformal Killing vector

$$
\xi
=
{\pi\over R}
\left[
\left(R^2-t^2-r^2\right)\partial_t
-2t x^i\partial_i
\right].
$$

At $t=0$, this reduces to

$$
\xi^0(t=0,\vec x)={\pi\over R}(R^2-r^2).
$$

Therefore the modular Hamiltonian is

$$
\boxed{
K_{B_R}
=
2\pi\int_{r<R} d^{d-1}x\,
{R^2-r^2\over 2R}
T_{00}(0,\vec x)
}
$$

again up to an additive constant if one uses the unnormalized convention.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Ball-region modular Hamiltonian and holographic RT surface](/figures/cft/entanglement-modular-hamiltonian-ball.svg)

<figcaption>

For the CFT vacuum, the reduced density matrix on a ball $B_R$ has a local modular Hamiltonian. The causal diamond $D(B_R)$ is conformal to $\mathbb R_\tau\times H^{d-1}$, where modular flow becomes time translation at inverse temperature $2\pi R$. In holographic CFTs, $S_{B_R}$ is computed by the RT surface $\gamma_{B_R}$ anchored on $\partial B_R$.

</figcaption>
</figure>

The factor

$$
{R^2-r^2\over 2R}
$$

is worth remembering. It vanishes at the entangling surface $r=R$, because the conformal Killing vector becomes null there. It is largest at the center of the ball. The modular Hamiltonian weights the energy density according to its position inside the causal diamond.

A useful explicit conformal map from the diamond to the hyperbolic cylinder is

$$
t={R\sinh(\tau/R)\over \cosh u+\cosh(\tau/R)},
\qquad
r={R\sinh u\over \cosh u+\cosh(\tau/R)}.
$$

The flat metric in the diamond becomes Weyl-equivalent to

$$
ds^2=-d\tau^2+R^2\left(du^2+\sinh^2u\,d\Omega_{d-2}^2\right).
$$

Thus the reduced vacuum density matrix is equivalent, in the hyperbolic frame, to

$$
\rho_{B_R}\sim e^{-2\pi R H_H},
$$

where $H_H$ is the Hamiltonian generating translations in $\tau$ on $H^{d-1}$. This is often the most efficient route to spherical entanglement entropy.

## Entanglement first law

Let $\rho_A$ be a reference reduced density matrix and let $\rho_A+\delta\rho_A$ be a nearby state with

$$
\operatorname{Tr}\delta\rho_A=0.
$$

The first-order variation of entropy is

$$
\delta S_A
= -\operatorname{Tr}(\delta\rho_A\log\rho_A)
= \operatorname{Tr}(\delta\rho_A K_A).
$$

Thus

$$
\boxed{
\delta S_A=\delta\langle K_A\rangle
}
$$

This is called the entanglement first law. It is not a thermodynamic assumption; it is a linear-algebra identity.

For a ball in the CFT vacuum, the first law gives the explicit formula

$$
\boxed{
\delta S_{B_R}
=
2\pi\int_{r<R}d^{d-1}x\,
{R^2-r^2\over 2R}\,
\delta\langle T_{00}(0,\vec x)\rangle
}
$$

for any sufficiently small perturbation of the state.

This equation is much more powerful than it first appears. In holographic CFTs, the left-hand side is the first variation of an area, while the right-hand side is the boundary energy. Requiring this equality for all balls is closely related to the linearized Einstein equation in the bulk.

## Relative entropy

The nonlinear version of the entanglement first law is relative entropy. Given two density matrices $\rho_A$ and $\sigma_A$, define

$$
S(\rho_A\|\sigma_A)
=
\operatorname{Tr}\rho_A\log\rho_A
-
\operatorname{Tr}\rho_A\log\sigma_A.
$$

Let

$$
K_A^{(\sigma)}=-\log\sigma_A.
$$

Then relative entropy can be written as

$$
\boxed{
S(\rho_A\|\sigma_A)
=\Delta\langle K_A^{(\sigma)}\rangle-\Delta S_A
\ge 0
}
$$

where

$$
\Delta\langle K_A^{(\sigma)}\rangle
=
\operatorname{Tr}\rho_AK_A^{(\sigma)}
-
\operatorname{Tr}\sigma_AK_A^{(\sigma)},
$$

and

$$
\Delta S_A=S_A(\rho)-S_A(\sigma).
$$

The inequality says

$$
\Delta S_A\le \Delta\langle K_A^{(\sigma)}\rangle.
$$

In words: entropy gain cannot exceed modular-energy gain. In holography, relative entropy becomes a positive bulk energy quantity. This is one of the cleanest ways in which unitarity and causality of the CFT constrain the bulk geometry.

The first law follows by expanding relative entropy around $\rho_A=\sigma_A$. Since relative entropy has a minimum at equality, its first variation vanishes:

$$
\delta S(\rho_A\|\sigma_A)=0
\quad\Longrightarrow\quad
\delta S_A=\delta\langle K_A^{(\sigma)}\rangle.
$$

## Mutual information

A useful finite quantity is the mutual information between two disjoint regions $A$ and $B$:

$$
I(A:B)=S_A+S_B-S_{A\cup B}.
$$

For separated regions, the short-distance divergences near $\partial A$ and $\partial B$ cancel, so $I(A:B)$ is cutoff independent. It is also nonnegative, because it can be written as a relative entropy:

$$
I(A:B)=S(\rho_{AB}\|\rho_A\otimes\rho_B)\ge 0.
$$

Mutual information is therefore a clean diagnostic of correlations between regions. In holographic large-$N$ CFTs, the leading RT answer for $I(A:B)$ can undergo a sharp transition when the minimal surface for $A\cup B$ changes topology. This transition is a geometric version of the statement that correlations between distant regions can become parametrically small at large $N$.

## Replica trick

The replica trick computes $S_A$ through the Rényi entropies. In Euclidean path-integral language,

$$
\operatorname{Tr}\rho_A^n
={Z_n(A)\over Z_1^n},
$$

where $Z_n(A)$ is the partition function on an $n$-sheeted geometry branched over the entangling surface $\partial A$.

Then

$$
S_A
=-\left.\partial_n\log\operatorname{Tr}\rho_A^n\right|_{n=1}.
$$

In two-dimensional CFT, the branch points can be represented by twist operators. For a single interval $A=[0,\ell]$ in the vacuum on the plane,

$$
\operatorname{Tr}\rho_A^n
=\langle\sigma_n(0)\widetilde\sigma_n(\ell)\rangle.
$$

For a parity-invariant CFT with $c_L=c_R=c$, the twist operator has dimensions

$$
h_n=\bar h_n={c\over 24}\left(n-{1\over n}\right).
$$

Therefore

$$
\operatorname{Tr}\rho_A^n
=c_n\left({\ell\over \epsilon}\right)^{-{c\over 6}(n-1/n)},
$$

and the Rényi entropy is

$$
\boxed{
S_n(A)
={c\over 6}\left(1+{1\over n}\right)
\log{\ell\over \epsilon}
+\text{constant}
}
$$

Taking $n\to 1$ gives

$$
\boxed{
S_A={c\over 3}\log{\ell\over \epsilon}+\text{constant}
}
$$

This derivation is a perfect example of the CFT philosophy: a seemingly nonlocal quantity, the entropy of a region, is computed by local operator data in a replicated theory.

## Holographic checkpoint: RT, HRT, and entanglement wedge

For a holographic CFT in a state with a classical static bulk dual, the Ryu-Takayanagi formula says

$$
\boxed{
S_A={\operatorname{Area}(\gamma_A)\over 4G_N}
}
$$

where $\gamma_A$ is the bulk minimal surface satisfying

$$
\partial\gamma_A=\partial A
$$

and homologous to $A$.

In time-dependent states, the Hubeny-Rangamani-Takayanagi prescription replaces $\gamma_A$ by an extremal surface. At the next order in the bulk semiclassical expansion, the entropy includes a bulk entanglement term:

$$
S_A
={\operatorname{Area}(\gamma_A)\over 4G_N}
+S_{\mathrm{bulk}}(\Sigma_A)
+\text{higher-order terms}.
$$

For the vacuum of a holographic CFT on flat space and a ball $B_R$, the RT surface in Poincaré AdS is a hemisphere,

$$
z^2+r^2=R^2,
\qquad t=0.
$$

The region between $B_R$ and $\gamma_{B_R}$ is the entanglement wedge. Roughly, it is the bulk region encoded by the boundary density matrix $\rho_{B_R}$. This idea becomes precise in quantum error-correction formulations of AdS/CFT.

The ball modular Hamiltonian is special because both sides are tractable:

$$
\text{CFT side: } K_{B_R}=2\pi\int_{B_R}{R^2-r^2\over 2R}T_{00},
$$

while

$$
\text{bulk side: } S_{B_R}={\operatorname{Area}(\gamma_{B_R})\over 4G_N}+\cdots.
$$

Equating their first variations is the entanglement first law. In holography, this becomes a gravitational first law for the corresponding Rindler wedge in AdS.

## Common pitfalls

The phrase “entanglement entropy of a CFT” always requires a region and a regulator. Only universal pieces are regulator independent.

The modular Hamiltonian is not usually the physical Hamiltonian. It becomes a familiar geometric generator only for special regions and special states, such as a half-space or a ball in the vacuum.

The equation $S_A=\langle K_A\rangle$ depends on the convention $K_A=-\log\rho_A$. If one writes $\rho_A=e^{-\widetilde K_A}/Z_A$, then $S_A=\langle\widetilde K_A\rangle+\log Z_A$.

The RT formula is not a definition of CFT entanglement entropy. It is a dynamical statement about holographic CFTs with a semiclassical gravity dual.

## What to remember

The reduced density matrix $\rho_A$ is the complete CFT object associated with a spatial region $A$. Its entropy $S_A$ is UV divergent, but its universal terms carry physical data. The modular Hamiltonian $K_A=-\log\rho_A$ is usually nonlocal, but for the vacuum half-space and vacuum ball it is a local stress-tensor integral. The entanglement first law

$$
\delta S_A=\delta\langle K_A\rangle
$$

is the linearized bridge between entropy and energy. In holographic CFTs, it becomes the bridge between boundary entanglement and bulk gravitational dynamics.

For AdS/CFT preparation, the most important formula on this page is

$$
K_{B_R}
=
2\pi\int_{r<R} d^{d-1}x\,
{R^2-r^2\over 2R}
T_{00}(0,\vec x).
$$

The second most important formula is

$$
S_A={\operatorname{Area}(\gamma_A)\over 4G_N}+\cdots.
$$

The first is pure CFT. The second is holography. Their compatibility is one of the deepest checks of AdS/CFT.

## Exercises

### Exercise 1: Entanglement first law from linear algebra

Let $\rho(\lambda)=\rho_0+\lambda\delta\rho+O(\lambda^2)$, with $\operatorname{Tr}\delta\rho=0$. Define $K_0=-\log\rho_0$. Show that

$$
\left.{d\over d\lambda}S(\rho(\lambda))\right|_{\lambda=0}
=
\operatorname{Tr}(\delta\rho K_0).
$$

<details><summary><strong>Solution</strong></summary>

The entropy is

$$
S(\rho)=-\operatorname{Tr}\rho\log\rho.
$$

For a small variation, the first variation is

$$
\delta S=-\operatorname{Tr}(\delta\rho\log\rho_0)-\operatorname{Tr}(\rho_0\delta\log\rho).
$$

The second term is

$$
\operatorname{Tr}(\rho_0\delta\log\rho)=\operatorname{Tr}\delta\rho,
$$

which vanishes because $\operatorname{Tr}\delta\rho=0$. Therefore

$$
\delta S=-\operatorname{Tr}(\delta\rho\log\rho_0)
=\operatorname{Tr}(\delta\rho K_0)
=\delta\langle K_0\rangle.
$$

</details>

### Exercise 2: Ball first law for constant energy density

Suppose a small perturbation of the vacuum has approximately constant energy density inside a ball:

$$
\delta\langle T_{00}\rangle=\varepsilon.
$$

Using the ball modular Hamiltonian, show that

$$
\delta S_{B_R}
={2\pi\Omega_{d-2}R^d\over d^2-1}\,\varepsilon,
$$

where $\Omega_{d-2}$ is the area of the unit $(d-2)$-sphere.

<details><summary><strong>Solution</strong></summary>

The first law gives

$$
\delta S_{B_R}
=2\pi\varepsilon
\int_{r<R}d^{d-1}x\,{R^2-r^2\over 2R}.
$$

Let $n=d-1$ be the number of spatial dimensions. Then

$$
d^{d-1}x=\Omega_{d-2}r^{d-2}dr.
$$

Thus

$$
\int_{r<R}d^{d-1}x\,{R^2-r^2\over 2R}
={\Omega_{d-2}\over 2R}
\int_0^R dr\, r^{d-2}(R^2-r^2).
$$

The radial integral is

$$
\int_0^R dr\, r^{d-2}(R^2-r^2)
=
R^{d+1}\left({1\over d-1}-{1\over d+1}\right)
={2R^{d+1}\over d^2-1}.
$$

Therefore

$$
\delta S_{B_R}
=2\pi\varepsilon\,{\Omega_{d-2}R^d\over d^2-1}.
$$

</details>

### Exercise 3: Interval entropy from twist operators

In a two-dimensional CFT with $c_L=c_R=c$, the twist operator for the $n$-replica theory has

$$
h_n=\bar h_n={c\over 24}\left(n-{1\over n}\right).
$$

Use the two-point function of twist operators to derive

$$
S_n={c\over 6}\left(1+{1\over n}\right)\log{\ell\over\epsilon}+\text{constant}.
$$

<details><summary><strong>Solution</strong></summary>

The replica partition function for one interval is proportional to the twist two-point function:

$$
\operatorname{Tr}\rho_A^n
=\langle\sigma_n(0)\widetilde\sigma_n(\ell)\rangle.
$$

A primary with dimensions $(h_n,\bar h_n)$ has two-point function

$$
\langle\sigma_n(0)\widetilde\sigma_n(\ell)\rangle
\propto
\ell^{-2h_n-2\bar h_n}.
$$

Restoring the cutoff gives

$$
\operatorname{Tr}\rho_A^n
=c_n\left({\ell\over\epsilon}\right)^{-2h_n-2\bar h_n}
=c_n\left({\ell\over\epsilon}\right)^{-{c\over 6}(n-1/n)}.
$$

Then

$$
S_n={1\over 1-n}\log\operatorname{Tr}\rho_A^n
={c\over 6}\left(1+{1\over n}\right)\log{\ell\over\epsilon}+\text{constant}.
$$

The $n\to 1$ limit gives $S_A={c\over 3}\log(\ell/\epsilon)+\text{constant}$.

</details>

### Exercise 4: Positivity of relative entropy and the first law

Let $\sigma_A$ be a reference state and $K_A^{(\sigma)}=-\log\sigma_A$. Show that

$$
S(\rho_A\|\sigma_A)
=\Delta\langle K_A^{(\sigma)}\rangle-\Delta S_A.
$$

Then explain why the first-order variation around $\rho_A=\sigma_A$ implies the entanglement first law.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
S(\rho_A\|\sigma_A)
=\operatorname{Tr}\rho_A\log\rho_A
-\operatorname{Tr}\rho_A\log\sigma_A.
$$

Using

$$
S_A(\rho)=-\operatorname{Tr}\rho_A\log\rho_A,
\qquad
K_A^{(\sigma)}=-\log\sigma_A,
$$

we get

$$
S(\rho_A\|\sigma_A)
=-S_A(\rho)+\operatorname{Tr}\rho_AK_A^{(\sigma)}.
$$

Subtract the same expression at $\rho_A=\sigma_A$. Since $S(\sigma_A\|\sigma_A)=0$, this gives

$$
S(\rho_A\|\sigma_A)
=\Delta\langle K_A^{(\sigma)}\rangle-\Delta S_A.
$$

Relative entropy is nonnegative and has a minimum at $\rho_A=\sigma_A$. Therefore its first variation vanishes around the reference state:

$$
\delta S(\rho_A\|\sigma_A)=0.
$$

Thus

$$
\delta\langle K_A^{(\sigma)}\rangle-\delta S_A=0,
$$

or

$$
\delta S_A=\delta\langle K_A^{(\sigma)}\rangle.
$$

</details>

### Exercise 5: Why the ball modular Hamiltonian is local

Explain why the modular Hamiltonian of a ball in the CFT vacuum is local, while the modular Hamiltonian of a generic shaped region is not expected to be local.

<details><summary><strong>Solution</strong></summary>

The half-space modular Hamiltonian is local because the vacuum restricted to a Rindler wedge is thermal with respect to the boost generator. A boost is generated by a local integral of $T_{00}$.

A ball-shaped domain of dependence is conformally equivalent to a Rindler wedge, or equivalently to $\mathbb R\times H^{d-1}$. Since a CFT maps local stress-tensor generators to local stress-tensor generators under conformal transformations, the ball modular Hamiltonian is also local:

$$
K_{B_R}=2\pi\int_{r<R}d^{d-1}x\,{R^2-r^2\over 2R}T_{00}.
$$

For a generic region, there is no conformal transformation mapping its causal domain to a geometric wedge with a simple Killing flow. The modular flow is then not generated by an ordinary spacetime symmetry. Consequently, $K_A=-\log\rho_A$ is generally a complicated nonlocal operator.

</details>

## Further reading

For the two-dimensional CFT side, read the DMS discussion of finite-size scaling, boundaries, modular methods, and the operator formalism. For modern AdS/CFT applications, the essential next readings are Ryu-Takayanagi, Hubeny-Rangamani-Takayanagi, Lewkowycz-Maldacena, Faulkner-Lewkowycz-Maldacena, and the JLMS relation between boundary and bulk modular Hamiltonians.
