---
title: "Radial Coordinates for Conformal Blocks"
description: "Defines the rho radial coordinate for four-point conformal blocks and explains why it gives rapidly convergent expansions for bootstrap computations."
sidebar:
  label: "Radial Coordinates"
  order: 4
level: Graduate
status: "Polished draft"
source: "Pappadopulo–Rychkov–Espin–Rattazzi 2012; Hogervorst–Rychkov 2013; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - radial coordinates
  - conformal blocks
  - rho coordinate
  - radial quantization
  - OPE convergence
  - numerical bootstrap
canonicalTopics:
  - radial-coordinates
  - conformal-block-expansion
  - conformal-blocks
  - radial-quantization
  - bootstrap-kinematics
researchStatus:
  established:
    - "The rho coordinate maps the Euclidean four-point OPE domain to a unit disk and gives rapidly convergent radial expansions of conformal blocks."
    - "Radial coordinates make the conformal block expansion look like a spectral decomposition in radial quantization."
  active:
    - "Efficient block generation for spinning operators, defects, supersymmetry, and high-precision mixed-correlator systems continues to use radial-coordinate ideas together with recursion and numerical approximation schemes."
---

## Summary

The **radial coordinate** $\rho$ is a better coordinate than $z$ for expanding conformal blocks. For a scalar four-point function, write the conformal cross-ratios as

$$
u = z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The radial coordinate is

$$
\rho
=
\frac{z}{\left(1+\sqrt{1-z}\right)^2}
=
\frac{1-\sqrt{1-z}}{1+\sqrt{1-z}},
\qquad
z=
\frac{4\rho}{(1+\rho)^2},
$$

and similarly for $\bar\rho$. In the Euclidean configuration, $\bar z=z^*$ and therefore $\bar\rho=\rho^*$. We often write

$$
\rho=r e^{i\theta},
\qquad
\bar\rho=r e^{-i\theta},
\qquad
\eta=\cos\theta.
$$

The point of this coordinate is not cosmetic. It turns the OPE expansion into an honest radial-quantization expansion whose small parameter is $r=|\rho|$. At the crossing-symmetric point $z=\bar z=1/2$,

$$
\rho=3-2\sqrt2\approx 0.1716,
$$

so expansions in powers of $\rho$ converge much faster than naive expansions in powers of $z$.

<figure class="doc-figure" style="--figure-width: 48rem;">

![The rho coordinate maps the cut z-plane to the unit rho disk and gives a symmetric radial four-point frame.](/figures/cft-bootstrap/rho-coordinate-geometry.svg)

<figcaption>

The map $z=4\rho/(1+\rho)^2$ sends the cut $z$-plane to the unit $\rho$ disk. In the radial conformal frame, the four operators sit at radii $r$ and $1$, so the block expansion becomes a spectral expansion in radial time.

</figcaption>
</figure>

## Prerequisites

You should know [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), [Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/), [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), and the [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/). The page uses Euclidean CFT conventions from [Conventions and Notation](/cft-bootstrap/conventions/).

## Core idea

The four-point function has many equivalent coordinate descriptions. The standard $z,\bar z$ variables are excellent for writing formulas, but they are not always the best variables for convergence. The reason is geometric: the nearest singularities of the Euclidean four-point function are controlled by when operators collide or cross branch cuts. In the $z$-plane, those singularities are awkwardly placed. The map to $\rho$ moves the relevant cut to the unit circle.

Radial quantization then gives the physical meaning. Place two operators on a sphere of radius $r$ and the other two on a sphere of radius $1$. Insert a complete set of states between the two spheres. Each state of scaling dimension $E$ contributes a factor $r^E$. Since descendants of a primary have dimensions $\Delta+n$, a conformal block becomes a power series in $r$.

That is the whole trick:

$$
\text{conformal block}
=
\text{sum over descendants}
=
\text{rapidly convergent radial series}.
$$

## Setup and conventions

Consider four scalar primaries $\mathcal O_i$ of dimensions $\Delta_i$. We write their four-point function in the standard form

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\mathcal G(u,v),
$$

where $\Delta_{ij}=\Delta_i-\Delta_j$ and

$$
u = z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The $\rho$ coordinate is defined by

$$
\rho = \frac{z}{\left(1+\sqrt{1-z}\right)^2},
\qquad
\bar\rho = \frac{\bar z}{\left(1+\sqrt{1-\bar z}\right)^2}.
$$

Equivalently,

$$
z = \frac{4\rho}{(1+\rho)^2},
\qquad
\bar z = \frac{4\bar\rho}{(1+\bar\rho)^2}.
$$

In the Euclidean region, $\rho$ and $\bar\rho$ are complex conjugates. We then define

$$
r = \sqrt{\rho\bar\rho},
\qquad
\eta = \frac{\rho+\bar\rho}{2\sqrt{\rho\bar\rho}}.
$$

Thus $\rho=re^{i\theta}$ and $\bar\rho=re^{-i\theta}$, with $\eta=\cos\theta$.

:::caution[Notation collision]
The symbol $r$ here is a dimensionless radial cross-ratio. It is not the spacetime radius $|x|$ of an arbitrary insertion. In the radial conformal frame the two notions are aligned, but only after a conformal transformation has fixed the four points.
:::

## The radial conformal frame

A useful representative of the four-point conformal orbit is

$$
x_1=-r n,
\qquad
x_2=r n,
\qquad
x_3=n',
\qquad
x_4=-n',
$$

where $n$ and $n'$ are unit vectors in a common two-plane and

$$
n\cdot n'=\eta=\cos\theta.
$$

The operators $\mathcal O_1$ and $\mathcal O_2$ are inserted on a sphere of radius $r$, while $\mathcal O_3$ and $\mathcal O_4$ are inserted on the unit sphere. The ordering $r<1$ is exactly the condition that the $12$ OPE channel is radially ordered inside the $34$ pair.

In this frame, the four-point function can be viewed as a matrix element between radial-quantization states:

$$
\langle
\mathcal O_3(n')\mathcal O_4(-n')
\mid
r^D
\mid
\mathcal O_1(-n)\mathcal O_2(n)
\rangle.
$$

The dilatation generator $D$ is the radial Hamiltonian. Inserting a complete set of energy eigenstates makes convergence transparent:

$$
r^D\mid \Psi_E\rangle = r^E \mid \Psi_E\rangle.
$$

For an exchanged primary of dimension $\Delta$, its descendants have dimensions $\Delta+n$ with $n=0,1,2,\ldots$. Therefore the conformal block has an expansion in powers of $r$.

## Radial expansion of a scalar block

For external scalars and an exchanged symmetric-traceless primary of dimension $\Delta$ and spin $\ell$, the block can be written schematically as

$$
g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(r,\eta)
=
(4r)^\Delta
\sum_{n=0}^{\infty} r^n
\sum_j
B_{n,j}^{\Delta_{12},\Delta_{34}}(\Delta,\ell)
C_j^{(\nu)}(\eta),
\qquad
\nu=\frac d2-1.
$$

Here $C_j^{(\nu)}(\eta)$ is a Gegenbauer polynomial. It records the spin-$j$ angular dependence of descendants at level $n$. The allowed $j$ values are fixed by tensoring the spin-$\ell$ primary with $n$ derivatives and then decomposing into irreducible representations of $SO(d)$.

The leading term has the expected OPE behavior:

$$
g_{\Delta,\ell}(r,\eta)
\sim
(4r)^\Delta C_\ell^{(\nu)}(\eta)
\qquad
r\to0,
$$

up to the block normalization convention. Different references distribute simple normalization factors between $g_{\Delta,\ell}$ and the OPE coefficients. What matters is that the convention is used consistently in crossing equations.

For $d=2$, the Gegenbauer notation becomes degenerate because $\nu=0$. Two-dimensional global blocks are better handled in complex coordinates or in holomorphic and anti-holomorphic variables. The idea of radial convergence still survives, but the bookkeeping changes.

## Why rho converges faster than z

The map

$$
\rho = \frac{1-\sqrt{1-z}}{1+\sqrt{1-z}}
$$

maps the complex $z$-plane cut along $[1,\infty)$ to the unit disk $|\rho|<1$. The inverse map

$$
z=\frac{4\rho}{(1+\rho)^2}
$$

sends the unit circle $|\rho|=1$ to the branch cut. Thus a Euclidean four-point configuration away from the cut has $|\rho|<1$.

This matters numerically. At the symmetric point,

$$
z=\bar z=\frac12
\qquad\Longrightarrow\qquad
\rho=\bar\rho=3-2\sqrt2\approx0.1716.
$$

So even a modest truncation in powers of $r$ can be accurate. In contrast, expanding directly in $z$ near $z=1/2$ is not nearly as efficient.

The radial expansion is also conceptually clean: the error after truncating descendants above level $N$ is controlled by omitted states of dimension roughly $\Delta+N$. The exact bound depends on normalization and on the correlator, but the physical reason for convergence is simple: high-energy radial states are suppressed by powers of $r$.

## Bootstrap role

Numerical bootstrap computations need many derivatives of conformal blocks near the crossing-symmetric point. Radial coordinates are useful because they turn those derivatives into derivatives of rapidly convergent series.

For identical external scalars, the crossing equation is commonly written as

$$
\sum_{\mathcal O}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0,
$$

where $F_{\Delta,\ell}$ is built from scalar blocks in two channels. To turn this into a numerical problem, one evaluates a finite list of derivatives of $F_{\Delta,\ell}$ at $z=\bar z=1/2$. The radial expansion is one of the workhorses behind making those derivatives accurate and efficient.

The positivity structure also becomes intuitive. In a unitary theory with identical external operators, the radial expansion may be viewed as a sum over positive-norm states inside a conformal multiplet. This does not mean every coefficient in every convention is positive, especially for unequal external operators or spinning structures. It means the spectral origin of the expansion is positive.

## Checks

**OPE limit.** As $r\to0$, the leading term must scale as $r^\Delta$ and carry the spin-$\ell$ angular dependence. If it does not, the block normalization or channel assignment is wrong.

**Symmetric point.** At $z=\bar z=1/2$, the coordinate is $\rho=3-2\sqrt2$. This small number is a useful sanity check for any code or notebook implementing the map.

**Euclidean conjugation.** In Euclidean kinematics, $\bar\rho$ is the complex conjugate of $\rho$. In Lorentzian kinematics, $z$ and $\bar z$ are often continued independently; then this statement no longer holds.

**Identity exchange.** The identity block does not have a tower of descendants. In the standard scalar four-point decomposition, it contributes the channel's disconnected or vacuum term, not a generic spin-$\ell$ radial series.

## Assumptions and status

- **Exact:** The change of variables from $z,\bar z$ to $\rho,\bar\rho$ is exact, and the radial-quantization interpretation of the Euclidean OPE is exact in a CFT.
- **Numerical:** Practical block computations truncate the radial series and estimate or control the truncation error.
- **Assumption-dependent:** Positivity statements depend on unitarity, reflection positivity, the external operators, and the normalization of tensor structures.
- **Open:** The best implementation strategy depends on the problem: scalar, spinning, supersymmetric, defect, and Lorentzian applications often require different recursions or basis choices.

## Common pitfalls

**Confusing z with rho.** The OPE limit $z\to0$ and $\rho\to0$ are equivalent, but the convergence properties away from the limit are very different.

**Forgetting the branch choice.** The square root in $\rho(z)$ is chosen so that $\rho\sim z/4$ near $z=0$. The wrong branch sends the OPE limit to infinity.

**Treating positivity as coefficient-by-coefficient magic.** Positivity is a Hilbert-space statement. It can be hidden by normalization choices, by non-identical external operators, or by tensor-structure bases.

**Using Euclidean intuition after Lorentzian continuation.** In Lorentzian regimes, $z$ and $\bar z$ can move around branch points independently. Radial coordinates remain useful, but the naive picture of conjugate points inside a disk may fail.

**Dropping the factor of four casually.** The leading behavior is often written as $(4r)^\Delta$ rather than $r^\Delta$. That factor is convention-dependent but important when comparing block tables or OPE coefficients across references.

## Relations to other pages

- [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) explains why dilatations act as Euclidean time evolution.
- [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) gives the operator-algebra reason the expansion is convergent.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) defines the block whose radial expansion is used here.
- [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) gives a differential equation that can determine radial coefficients.
- [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/) explains practical algorithms for generating conformal blocks from radial expansions and analytic structure.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) uses these blocks as the building blocks of bootstrap equations.

## Research status

Radial coordinates are settled technology in the scalar conformal bootstrap and are part of the standard explanation of why block computations are tractable. The active work is not whether $\rho$ is useful; it is how to combine radial variables, recursion relations, rational approximations, symmetry-adapted tensor bases, and high-precision numerics for more complicated bootstrap systems.

In Lorentzian and analytic bootstrap applications, radial variables are often supplemented by lightcone variables, Regge variables, or other continuations adapted to causal ordering. Those are not contradictions. They are different coordinate choices optimized for different physical limits.

## Exercises

### Exercise 1: Invert the rho map

Starting from

$$
\rho=\frac{1-\sqrt{1-z}}{1+\sqrt{1-z}},
$$

show that

$$
z=\frac{4\rho}{(1+\rho)^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Let $s=\sqrt{1-z}$. Then

$$
\rho=\frac{1-s}{1+s}
\qquad\Longrightarrow\qquad
s=\frac{1-\rho}{1+\rho}.
$$

Therefore

$$
1-z=s^2=\left(\frac{1-\rho}{1+\rho}\right)^2,
$$

so

$$
z
=1-\frac{(1-\rho)^2}{(1+\rho)^2}
=\frac{(1+\rho)^2-(1-\rho)^2}{(1+\rho)^2}
=\frac{4\rho}{(1+\rho)^2}.
$$

</details>

### Exercise 2: The symmetric point

Evaluate $\rho$ at $z=1/2$ and show that

$$
\rho=3-2\sqrt2.
$$

<details>
<summary><strong>Solution</strong></summary>

At $z=1/2$,

$$
\sqrt{1-z}=\frac{1}{\sqrt2}.
$$

Thus

$$
\rho
=
\frac{1-1/\sqrt2}{1+1/\sqrt2}
=
\frac{\sqrt2-1}{\sqrt2+1}
=
(\sqrt2-1)^2
=
3-2\sqrt2.
$$

Numerically this is about $0.1716$.

</details>

### Exercise 3: Leading radial behavior

Assume that a primary of dimension $\Delta$ is exchanged in the $12$ OPE channel. Explain why the leading block contribution must scale as $r^\Delta$ as $r\to0$.

<details>
<summary><strong>Solution</strong></summary>

In radial quantization, inserting the exchanged primary between the inner and outer spheres gives a state with radial energy $\Delta$. Radial time evolution from radius $1$ to radius $r$ contributes $r^D$. Acting on the primary state, this gives $r^\Delta$. Descendants have dimensions $\Delta+n$, so they are suppressed by additional powers $r^n$.

</details>

### Exercise 4: Why the diagonal point is numerically gentle

Compare $z=1/2$ and $\rho=3-2\sqrt2$ as expansion parameters. Estimate the size of the tenth power of each.

<details>
<summary><strong>Solution</strong></summary>

One has

$$
\left(\frac12\right)^{10}\approx 9.77\times10^{-4},
$$

whereas

$$
(3-2\sqrt2)^{10}\approx 2.2\times10^{-8}.
$$

This crude comparison is not a rigorous truncation bound for a conformal block, but it explains why a radial expansion can be dramatically more efficient near the crossing-symmetric point.

</details>

## References

### Standard first pass

- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D Greater Than or Equal to Three Dimensions*, 2016.
- David Simmons-Duffin, *The Conformal Bootstrap*, TASI lectures, 2017.
- David Poland, Slava Rychkov, and Alessandro Vichi, *The Conformal Bootstrap: Theory, Numerical Techniques, and Applications*, 2019.

### Deeper references

- Miguel S. Costa, Joao Penedones, David Poland, and Slava Rychkov, *Spinning Conformal Correlators*, 2011.
- D. Pappadopulo, Slava Rychkov, Johnny Espin, and Riccardo Rattazzi, *OPE Convergence in Conformal Field Theory*, 2012.
- Matthijs Hogervorst and Slava Rychkov, *Radial Coordinates for Conformal Blocks*, 2013.
- Matthijs Hogervorst, Hugh Osborn, and Slava Rychkov, work on diagonal limits and recursion methods for conformal blocks.

## Version history

- **2026-06-27:** Initial polished draft for the Conformal Blocks chapter.
