---
title: "Problem Sets and Projects"
description: "Exercises, solutions, and mini-projects for Modern CFT for AdS/CFT."
sidebar:
  order: 5
---

This appendix is the working laboratory for the course. The lectures explain the logic of conformal field theory; the problems make that logic usable. The goal is not to accumulate tricks, but to develop the habits that matter for AdS/CFT:

$$
\text{symmetry}
\longrightarrow
\text{Ward identities}
\longrightarrow
\text{operator data}
\longrightarrow
\text{crossing}
\longrightarrow
\text{large-}N
\longrightarrow
\text{bulk interpretation}.
$$

A good solution should usually include three layers: the physical meaning, the algebra, and the holographic checkpoint. A correct formula with no explanation is not yet a good solution; a beautiful explanation with no formula is not yet a CFT solution. The sweet spot is both.

## How to use this page

The problems below are organized as cumulative problem sets. The first half builds the core CFT machinery; the second half turns it into AdS/CFT readiness. Many problems include complete solutions. Some mini-projects are deliberately open-ended, because graduate-level mastery requires producing a coherent derivation, not only checking boxes.

A reasonable one-semester rhythm is:

| Weeks | Suggested assignment | Main skill |
|---:|---|---|
| 1--2 | Problem Sets 1--2 | QFT data, RG, critical exponents |
| 3--4 | Problem Sets 3--4 | conformal group, correlators, Ward identities |
| 5--6 | Problem Sets 5--6 | radial quantization, OPE, conformal blocks |
| 7--8 | Problem Sets 7--8 | Virasoro, minimal models, modular invariance |
| 9--10 | Problem Sets 9--10 | thermal CFT, entanglement, supersymmetry |
| 11--12 | Problem Sets 11--12 | large-$N$, $\mathcal N=4$ SYM, pre-dictionary |
| 13--14 | one mini-project | synthesis and presentation |

Throughout this page, local operators are normalized in CFT conventions, not Lagrangian conventions. For example, for scalar primaries we often write

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}},
$$

after choosing an orthonormal basis of scalar primaries with equal spin and global-symmetry quantum numbers.

## Problem Set 1: QFT data and sources

### Problem 1.1: Connected correlators from $W[J]$

Let

$$
Z[J]
=
\left\langle \exp\left(\int d^d x\,J(x)\mathcal O(x)\right)\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Show that functional derivatives of $W[J]$ generate connected correlation functions. In particular, show that

$$
\frac{\delta W}{\delta J(x)}=\langle \mathcal O(x)\rangle_J,
$$

and

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\langle \mathcal O(x)\mathcal O(y)\rangle_J
-
\langle \mathcal O(x)\rangle_J\langle \mathcal O(y)\rangle_J.
$$

Explain why this is the field-theory ancestor of the AdS/CFT statement

$$
Z_{\mathrm{CFT}}[J]=Z_{\mathrm{bulk}}[\phi_{\partial}=J].
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\frac{\delta Z[J]}{\delta J(x)}
=
\left\langle \mathcal O(x)
\exp\left(\int d^d y\,J(y)\mathcal O(y)\right)\right\rangle.
$$

Dividing by $Z[J]$ gives the expectation value in the source-deformed ensemble,

$$
\frac{\delta W}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}
=
\langle \mathcal O(x)\rangle_J.
$$

For the second derivative,

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\frac{1}{Z}\frac{\delta^2 Z}{\delta J(x)\delta J(y)}
-
\frac{1}{Z^2}\frac{\delta Z}{\delta J(x)}\frac{\delta Z}{\delta J(y)}.
$$

The first term is $\langle \mathcal O(x)\mathcal O(y)\rangle_J$ and the second is the product of one-point functions. Therefore

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\langle \mathcal O(x)\mathcal O(y)\rangle_{J,c}.
$$

Higher derivatives of $W$ similarly generate connected correlators.

In AdS/CFT, $J(x)$ is not just a bookkeeping device. It is the boundary value of a bulk field $\phi$ dual to $\mathcal O$. Therefore the same operation that differentiates $W_{\mathrm{CFT}}[J]$ with respect to $J$ becomes, on the bulk side, a variation of the renormalized on-shell gravitational action with respect to the boundary condition of $\phi$.

</details>

### Problem 1.2: Contact terms and source redefinitions

Suppose one changes the source-dependent generating functional by a local counterterm

$$
W[J]\mapsto W[J]+\frac{a}{2}\int d^d x\,J(x)^2.
$$

What happens to the two-point function? Why is this a contact-term ambiguity rather than a change of separated-point CFT data?

<details><summary><strong>Solution</strong></summary>

Taking two derivatives gives

$$
\frac{\delta^2}{\delta J(x)\delta J(y)}
\left[\frac{a}{2}\int d^d z\,J(z)^2\right]
=
a\delta^{(d)}(x-y).
$$

Therefore

$$
\langle \mathcal O(x)\mathcal O(y)\rangle_c
\mapsto
\langle \mathcal O(x)\mathcal O(y)\rangle_c+a\delta^{(d)}(x-y).
$$

For $x\ne y$, the correlator is unchanged. The local counterterm only changes coincident-point information. This is why separated-point CFT data such as scaling dimensions and OPE coefficients are scheme-independent, while contact terms require conventions.

In holographic renormalization, precisely such local source counterterms are added to make the on-shell bulk action finite. They change contact terms but not the nonlocal correlator.

</details>

## Problem Set 2: RG and critical data

### Problem 2.1: Linearized beta functions

Deform a CFT by scalar primaries,

$$
S=S_{\mathrm{CFT}}+\sum_i g_i\int d^d x\,\mathcal O_i(x),
\qquad
\Delta_i=\Delta(\mathcal O_i).
$$

Define dimensionless couplings

$$
\lambda_i(\mu)=g_i\mu^{\Delta_i-d}.
$$

Show that, to first order near the fixed point,

$$
\beta_i(\lambda)=\mu\frac{d\lambda_i}{d\mu}
=(\Delta_i-d)\lambda_i+O(\lambda^2).
$$

Classify relevant, marginal, and irrelevant operators.

<details><summary><strong>Solution</strong></summary>

Since $g_i$ has engineering dimension

$$
[g_i]=d-\Delta_i,
$$

the dimensionless coupling is $\lambda_i=g_i\mu^{\Delta_i-d}$. Holding the bare deformation fixed and differentiating with respect to $\mu$ gives

$$
\mu\frac{d\lambda_i}{d\mu}
=(\Delta_i-d)g_i\mu^{\Delta_i-d}+O(\lambda^2)
=(\Delta_i-d)\lambda_i+O(\lambda^2).
$$

Thus:

| Operator | Condition | Linearized behavior |
|---|---:|---|
| relevant | $\Delta_i<d$ | grows toward the IR |
| marginal | $\Delta_i=d$ | decided by $O(\lambda^2)$ terms |
| irrelevant | $\Delta_i>d$ | dies toward the IR |

The phrase “toward the IR” means lowering the physical energy scale. Since the beta function above is written with respect to $\mu$, the sign should be interpreted carefully: for $\Delta_i<d$, the dimensionful effect of $g_i$ becomes larger at long distances.

</details>

### Problem 2.2: Critical exponents from operator dimensions

Let a statistical critical point be described by a CFT. Suppose the thermal deformation is controlled by a scalar operator $\epsilon$ of dimension $\Delta_\epsilon$, and the magnetic field couples to a scalar order parameter $\sigma$ of dimension $\Delta_\sigma$:

$$
S=S_{\mathrm{CFT}}+t\int d^d x\,\epsilon(x)-h\int d^d x\,\sigma(x).
$$

Show that

$$
\nu=\frac{1}{d-\Delta_\epsilon},
\qquad
\eta=2\Delta_\sigma-d+2,
$$

and

$$
\gamma=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

The thermal coupling $t$ has RG eigenvalue

$$
y_t=d-\Delta_\epsilon.
$$

The correlation length scales as the inverse RG scale at which the dimensionless thermal perturbation becomes order one:

$$
\xi\sim |t|^{-1/y_t}.
$$

Thus

$$
\nu=\frac{1}{y_t}=\frac{1}{d-\Delta_\epsilon}.
$$

At criticality,

$$
\langle \sigma(x)\sigma(0)\rangle\sim \frac{1}{|x|^{2\Delta_\sigma}}.
$$

In statistical-mechanics notation,

$$
\langle \sigma(x)\sigma(0)\rangle\sim \frac{1}{|x|^{d-2+\eta}}.
$$

Equating powers gives

$$
2\Delta_\sigma=d-2+\eta,
$$

so

$$
\eta=2\Delta_\sigma-d+2.
$$

The susceptibility is the integrated connected two-point function cut off at the correlation length:

$$
\chi\sim \int^{\xi} d^d x\,\frac{1}{|x|^{2\Delta_\sigma}}
\sim \xi^{d-2\Delta_\sigma}.
$$

Using $\xi\sim |t|^{-\nu}$ gives

$$
\chi\sim |t|^{-\nu(d-2\Delta_\sigma)}.
$$

Therefore

$$
\gamma=\nu(d-2\Delta_\sigma)
=\frac{d-2\Delta_\sigma}{d-\Delta_\epsilon}.
$$

</details>

## Problem Set 3: Conformal geometry and algebra

### Problem 3.1: Finite special conformal transformations

A special conformal transformation can be written as inversion, translation, inversion:

$$
x^\mu\mapsto \frac{x^\mu}{x^2},
\qquad
\frac{x^\mu}{x^2}\mapsto \frac{x^\mu}{x^2}-b^\mu,
\qquad
\frac{x^\mu}{x^2}-b^\mu\mapsto x'^\mu.
$$

Show that

$$
x'^\mu=\frac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2}.
$$

Then expand to first order in $b^\mu$ and identify the infinitesimal vector field.

<details><summary><strong>Solution</strong></summary>

Let

$$
y^\mu=\frac{x^\mu}{x^2}-b^\mu.
$$

The final inversion gives

$$
x'^\mu=\frac{y^\mu}{y^2}.
$$

Compute

$$
y^2=\left(\frac{x}{x^2}-b\right)^2
=\frac{1}{x^2}-\frac{2b\cdot x}{x^2}+b^2
=\frac{1-2b\cdot x+b^2x^2}{x^2}.
$$

Therefore

$$
x'^\mu
=
\frac{x^\mu/x^2-b^\mu}{(1-2b\cdot x+b^2x^2)/x^2}
=
\frac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2}.
$$

To first order in $b$,

$$
x'^\mu=(x^\mu-b^\mu x^2)(1+2b\cdot x)+O(b^2),
$$

so

$$
\delta x^\mu=x'^\mu-x^\mu
=2(b\cdot x)x^\mu-b^\mu x^2.
$$

The corresponding infinitesimal vector field is

$$
\xi_b=\left(2(b\cdot x)x^\mu-b^\mu x^2\right)\partial_\mu.
$$

Up to the conventional factor of $-i$, this is the special conformal generator $b^\mu K_\mu$.

</details>

### Problem 3.2: The commutator $[K_\mu,P_\nu]$

Using the differential-operator representation

$$
P_\mu=-i\partial_\mu,
\qquad
D=-ix^\rho\partial_\rho,
\qquad
M_{\mu\nu}=i(x_\mu\partial_\nu-x_\nu\partial_\mu),
$$

and

$$
K_\mu=-i(2x_\mu x^\rho\partial_\rho-x^2\partial_\mu),
$$

show that

$$
[K_\mu,P_\nu]=2i(\delta_{\mu\nu}D-M_{\mu\nu})
$$

in Euclidean signature.

<details><summary><strong>Solution</strong></summary>

It is enough to act on a test function $f(x)$. Write

$$
K_\mu=-iV_\mu,
\qquad
P_\nu=-i\partial_\nu,
$$

where

$$
V_\mu=2x_\mu x^\rho\partial_\rho-x^2\partial_\mu.
$$

Then

$$
[K_\mu,P_\nu]=-[V_\mu,\partial_\nu].
$$

For a vector field $V=V^\rho\partial_\rho$,

$$
[V,\partial_\nu]=-(\partial_\nu V^\rho)\partial_\rho.
$$

Here

$$
V_\mu{}^\rho=2x_\mu x^\rho-x^2\delta_\mu{}^\rho,
$$

so

$$
\partial_\nu V_\mu{}^\rho
=2\delta_{\mu\nu}x^\rho+2x_\mu\delta_\nu{}^\rho-2x_\nu\delta_\mu{}^\rho.
$$

Thus

$$
[K_\mu,P_\nu]
=\left(2\delta_{\mu\nu}x^\rho\partial_\rho+2x_\mu\partial_\nu-2x_\nu\partial_\mu\right).
$$

Using

$$
x^\rho\partial_\rho=iD,
\qquad
x_\mu\partial_\nu-x_\nu\partial_\mu=-iM_{\mu\nu},
$$

we obtain

$$
[K_\mu,P_\nu]
=2i\delta_{\mu\nu}D-2iM_{\mu\nu}
=2i(\delta_{\mu\nu}D-M_{\mu\nu}).
$$

Different sign conventions for $M_{\mu\nu}$ shift the sign in the second term; the physics is unchanged once conventions are used consistently.

</details>

## Problem Set 4: Correlation functions and Ward identities

### Problem 4.1: Scalar three-point functions

Use conformal invariance to derive the form of the scalar three-point function

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle.
$$

Assume $\mathcal O_i$ are scalar primaries of dimensions $\Delta_i$.

<details><summary><strong>Solution</strong></summary>

Translation and rotation invariance imply that the correlator depends only on distances $x_{ij}=|x_i-x_j|$. Scale covariance suggests

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\frac{C_{123}}{x_{12}^{a}x_{23}^{b}x_{13}^{c}}.
$$

Under $x_i\mapsto \lambda x_i$, the correlator must scale as

$$
\lambda^{-(\Delta_1+\Delta_2+\Delta_3)}.
$$

Thus

$$
a+b+c=\Delta_1+\Delta_2+\Delta_3.
$$

Special conformal covariance, or equivalently inversion covariance, fixes how powers attach to each point. Under inversion $x^\mu\mapsto x^\mu/x^2$,

$$
x_{ij}\mapsto \frac{x_{ij}}{|x_i||x_j|},
$$

and a scalar primary transforms with a factor $|x_i|^{2\Delta_i}$. Matching the powers of each $|x_i|$ gives

$$
a+c=2\Delta_1,
\qquad
 a+b=2\Delta_2,
\qquad
 b+c=2\Delta_3.
$$

Solving,

$$
a=\Delta_1+\Delta_2-\Delta_3,
$$

$$
b=\Delta_2+\Delta_3-\Delta_1,
$$

$$
c=\Delta_1+\Delta_3-\Delta_2.
$$

Therefore

$$
\boxed{
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=
\frac{C_{123}}{
 x_{12}^{\Delta_1+\Delta_2-\Delta_3}
 x_{23}^{\Delta_2+\Delta_3-\Delta_1}
 x_{13}^{\Delta_1+\Delta_3-\Delta_2}}
}.
$$

The coefficient $C_{123}$ is dynamical CFT data.

</details>

### Problem 4.2: Current two-point function

For a conserved spin-one current in a $d$-dimensional CFT, the two-point function is

$$
\langle J_\mu(x)J_\nu(0)\rangle
=
\frac{C_J I_{\mu\nu}(x)}{x^{2(d-1)}},
$$

where

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

Show that it is conserved for $x\ne 0$:

$$
\partial^\mu\langle J_\mu(x)J_\nu(0)\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Let $r^2=x^2$. We need

$$
\partial^\mu\left(\frac{I_{\mu\nu}}{r^{2(d-1)}}\right)=0.
$$

Write

$$
\frac{I_{\mu\nu}}{r^{2(d-1)}}
=
\frac{\delta_{\mu\nu}}{r^{2d-2}}
-2\frac{x_\mu x_\nu}{r^{2d}}.
$$

The derivative of the first term is

$$
\partial^\mu\left(\frac{\delta_{\mu\nu}}{r^{2d-2}}\right)
=-(2d-2)\frac{x_\nu}{r^{2d}}.
$$

For the second term,

$$
\partial^\mu\left(\frac{x_\mu x_\nu}{r^{2d}}\right)
=
\frac{(d+1)x_\nu}{r^{2d}}-2d\frac{x^2x_\nu}{r^{2d+2}}
=
\frac{(d+1)x_\nu}{r^{2d}}-2d\frac{x_\nu}{r^{2d}}
=
(1-d)\frac{x_\nu}{r^{2d}}.
$$

Multiplying by $-2$ gives

$$
-2\partial^\mu\left(\frac{x_\mu x_\nu}{r^{2d}}\right)
=2(d-1)\frac{x_\nu}{r^{2d}}.
$$

This cancels the derivative of the first term. Therefore the correlator is conserved away from contact terms at $x=0$.

</details>

## Problem Set 5: Radial quantization and unitarity

### Problem 5.1: Cylinder energies from scaling dimensions

Let a scalar primary $\mathcal O$ of dimension $\Delta$ create a radial-quantization state

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

Use the plane-cylinder map $r=e^\tau$ to show that the cylinder Hamiltonian is the dilatation operator and that

$$
H_{\mathrm{cyl}}|\mathcal O\rangle=\Delta |\mathcal O\rangle.
$$

<details><summary><strong>Solution</strong></summary>

On $\mathbb R^d\setminus\{0\}$, write the flat metric as

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2.
$$

With $r=e^\tau$,

$$
ds^2=e^{2\tau}(d\tau^2+d\Omega_{d-1}^2).
$$

After a Weyl transformation, this is the cylinder metric on $\mathbb R_\tau\times S^{d-1}$. Translation in cylinder time $\tau$ is radial scaling on the plane:

$$
\tau\mapsto \tau+a
\quad\Longleftrightarrow\quad
r\mapsto e^a r.
$$

Thus the Hamiltonian generating cylinder time translations is the dilatation generator $D$.

A primary obeys

$$
D\mathcal O(0)|0\rangle=\Delta\mathcal O(0)|0\rangle,
$$

so

$$
H_{\mathrm{cyl}}|\mathcal O\rangle=\Delta|\mathcal O\rangle.
$$

This is the seed of the AdS interpretation: CFT operator dimensions are energies of states on the cylinder, matching global AdS energies.

</details>

### Problem 5.2: Scalar unitarity bound

For a scalar primary $|\Delta\rangle$, positivity of descendants implies the unitarity bound

$$
\Delta\ge \frac{d-2}{2},
$$

except for the identity operator. Show how this bound arises from the norm of the level-two scalar descendant $P^2|\Delta\rangle$.

<details><summary><strong>Solution</strong></summary>

In radial quantization,

$$
P_\mu^\dagger=K_\mu.
$$

The norm of the level-two scalar descendant is

$$
\|P^2|\Delta\rangle\|^2
=\langle \Delta|K^2P^2|\Delta\rangle.
$$

Using the conformal algebra and the primary conditions

$$
K_\mu|\Delta\rangle=0,
\qquad
M_{\mu\nu}|\Delta\rangle=0,
\qquad
D|\Delta\rangle=\Delta|\Delta\rangle,
$$

one finds, up to a positive normalization convention,

$$
\langle \Delta|K^2P^2|\Delta\rangle
\propto
\Delta\left(\Delta-\frac{d-2}{2}\right)\langle \Delta|\Delta\rangle.
$$

The level-one descendants already require $\Delta\ge 0$. For a non-identity scalar, positivity of the level-two norm then requires

$$
\Delta\ge \frac{d-2}{2}.
$$

At saturation, $P^2|\Delta\rangle$ is null. In operator language,

$$
\partial^2\mathcal O=0,
$$

so the operator behaves like a free scalar field. This is why saturation of a unitarity bound usually means a shortening condition.

</details>

## Problem Set 6: OPE, blocks, and crossing

### Problem 6.1: Crossing equation for identical scalars

For identical scalar primaries $\phi$ of dimension $\Delta_\phi$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}G(u,v),
$$

with cross-ratios

$$
 u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
 \qquad
 v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Derive the crossing equation relating $G(u,v)$ and $G(v,u)$ under $x_1\leftrightarrow x_3$.

<details><summary><strong>Solution</strong></summary>

Under the exchange $x_1\leftrightarrow x_3$, the cross-ratios transform as

$$
 u\leftrightarrow v.
$$

The same four-point function can be written in the exchanged channel as

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{x_{23}^{2\Delta_\phi}x_{14}^{2\Delta_\phi}}G(v,u).
$$

Equating this with the original representation gives

$$
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}G(u,v)
=
\frac{1}{x_{23}^{2\Delta_\phi}x_{14}^{2\Delta_\phi}}G(v,u).
$$

Using

$$
\frac{x_{12}^2x_{34}^2}{x_{14}^2x_{23}^2}=\frac{u}{v},
$$

we get

$$
\boxed{
G(u,v)=\left(\frac{u}{v}\right)^{\Delta_\phi}G(v,u)
}.
$$

This is the simplest bootstrap equation. Expanded in conformal blocks, it becomes a constraint on the spectrum and OPE coefficients appearing in the $\phi\times\phi$ OPE.

</details>

### Problem 6.2: Block expansion and positivity

Assume the identical-scalar four-point function has the conformal block expansion

$$
G(u,v)=\sum_{\mathcal O\in \phi\times\phi}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v),
$$

where the exchanged operators are primaries of dimension $\Delta$ and spin $\ell$. Explain why the coefficients are nonnegative in a unitary CFT, after choosing real normalized operators.

<details><summary><strong>Solution</strong></summary>

The OPE has the schematic form

$$
\phi(x)\phi(0)\sim \sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}\,C_{\Delta,\ell}(x,\partial)\mathcal O(0),
$$

where $C_{\Delta,\ell}$ is fixed by conformal symmetry. In a basis where two-point functions of primaries are diagonal and positive,

$$
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle\propto \delta_{ab},
$$

the four-point function contribution of a given conformal family is proportional to the product of the OPE coefficient in the left OPE and the OPE coefficient in the right OPE. For identical external operators these two coefficients are the same:

$$
\lambda_{\phi\phi\mathcal O}\lambda_{\phi\phi\mathcal O}
=\lambda_{\phi\phi\mathcal O}^2.
$$

Reflection positivity allows the coefficients to be chosen real. Hence

$$
\lambda_{\phi\phi\mathcal O}^2\ge 0.
$$

This positivity is the key input that turns crossing symmetry from a formal associativity equation into a powerful numerical bootstrap constraint.

</details>

### Problem 6.3: Generalized free field spectrum

Let $\mathcal O$ be a generalized free scalar of dimension $\Delta$. Its four-point function is

$$
G(u,v)=1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

Explain why the $\mathcal O\times\mathcal O$ OPE contains double-trace primaries with schematic form

$$
[\mathcal O\mathcal O]_{n,\ell}
\sim
\mathcal O\,\partial^{2n}\partial_{\mu_1}\cdots\partial_{\mu_\ell}\mathcal O-\text{traces},
$$

and dimensions

$$
\Delta_{n,\ell}=2\Delta+2n+\ell.
$$

<details><summary><strong>Solution</strong></summary>

The generalized free four-point function is obtained by Wick-like pairings, even though $\mathcal O$ need not be a fundamental free field. In the $12\to34$ channel, the identity comes from the disconnected pairing

$$
\langle \mathcal O_1\mathcal O_2\rangle\langle \mathcal O_3\mathcal O_4\rangle.
$$

The remaining pairings must be reproduced by an infinite tower of nontrivial conformal families in the $\mathcal O\times\mathcal O$ OPE. Since the theory is generalized free at leading order, the two-particle operators behave like normal-ordered products of two independent one-particle operators.

Each $\mathcal O$ contributes dimension $\Delta$. Derivatives contribute one unit of dimension. A spin-$\ell$ symmetric traceless tensor needs $\ell$ uncontracted derivatives. Radial excitations are represented by $2n$ extra contracted derivatives. Therefore

$$
\Delta_{n,\ell}=\Delta+\Delta+\ell+2n
=2\Delta+2n+\ell.
$$

In AdS, these are precisely two-particle states made from two identical bulk quanta in global AdS. The integer $n$ is a radial excitation number and $\ell$ is angular momentum.

</details>

## Problem Set 7: Essential two-dimensional CFT

### Problem 7.1: Virasoro algebra from the $T T$ OPE

Assume the holomorphic stress tensor has OPE

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

With modes

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z),
$$

derive

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

<details><summary><strong>Solution</strong></summary>

The commutator is computed by nested contour integrals:

$$
[L_m,L_n]
=
\frac{1}{(2\pi i)^2}\oint_w dw\,w^{n+1}\oint_{z=w}dz\,z^{m+1}T(z)T(w).
$$

Insert the singular part of the OPE. The central term is

$$
\frac{c}{2}\frac{1}{2\pi i}\oint dw\,w^{n+1}
\frac{1}{2\pi i}\oint_{z=w}dz\,\frac{z^{m+1}}{(z-w)^4}.
$$

Using

$$
\frac{1}{2\pi i}\oint_{z=w}dz\,\frac{z^{m+1}}{(z-w)^4}
=\frac{1}{3!}\partial_w^3 w^{m+1}
=\frac{(m+1)m(m-1)}{6}w^{m-2},
$$

the central contribution becomes

$$
\frac{c}{12}m(m^2-1)\frac{1}{2\pi i}\oint dw\,w^{m+n-1}
=
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The $2T(w)/(z-w)^2$ term gives

$$
2(m+1)\frac{1}{2\pi i}\oint dw\,w^{m+n+1}T(w)
=2(m+1)L_{m+n}.
$$

The $\partial T(w)/(z-w)$ term gives

$$
\frac{1}{2\pi i}\oint dw\,w^{m+n+2}\partial T(w)
=-(m+n+2)L_{m+n},
$$

after integration by parts. Combining these two noncentral terms gives

$$
2(m+1)-(m+n+2)=m-n.
$$

Hence

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

</details>

### Problem 7.2: Null vector at level two

Consider a Virasoro highest-weight state $|h\rangle$. A level-two descendant has form

$$
|\chi\rangle=(L_{-2}+aL_{-1}^2)|h\rangle.
$$

Find the conditions for $|\chi\rangle$ to be null, meaning

$$
L_1|\chi\rangle=0,
\qquad
L_2|\chi\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
[L_1,L_{-2}]=3L_{-1},
\qquad
[L_1,L_{-1}]=2L_0.
$$

Since $L_1|h\rangle=0$,

$$
L_1L_{-2}|h\rangle=3L_{-1}|h\rangle.
$$

Also

$$
L_1L_{-1}^2|h\rangle
=[L_1,L_{-1}]L_{-1}|h\rangle+L_{-1}[L_1,L_{-1}]|h\rangle.
$$

Using $L_0L_{-1}|h\rangle=(h+1)L_{-1}|h\rangle$ and $L_0|h\rangle=h|h\rangle$, this gives

$$
L_1L_{-1}^2|h\rangle
=2(h+1)L_{-1}|h\rangle+2hL_{-1}|h\rangle
=(4h+2)L_{-1}|h\rangle.
$$

Therefore $L_1|\chi\rangle=0$ implies

$$
3+a(4h+2)=0,
$$

so

$$
a=-\frac{3}{2(2h+1)}.
$$

Next use

$$
[L_2,L_{-2}]=4L_0+\frac{c}{2},
\qquad
[L_2,L_{-1}]=3L_1.
$$

Thus

$$
L_2L_{-2}|h\rangle=\left(4h+\frac{c}{2}\right)|h\rangle.
$$

For the other term,

$$
L_2L_{-1}^2|h\rangle
=[L_2,L_{-1}]L_{-1}|h\rangle+L_{-1}[L_2,L_{-1}]|h\rangle.
$$

The second term vanishes because $L_1|h\rangle=0$. The first gives

$$
3L_1L_{-1}|h\rangle=3(2h)|h\rangle=6h|h\rangle.
$$

So $L_2|\chi\rangle=0$ implies

$$
4h+\frac{c}{2}+6ah=0.
$$

Substituting $a=-3/[2(2h+1)]$ gives the level-two degeneracy condition

$$
4h+\frac{c}{2}-\frac{9h}{2h+1}=0.
$$

Equivalently,

$$
c=\frac{2h(5-8h)}{2h+1}.
$$

This is the algebraic origin of second-order BPZ equations.

</details>

## Problem Set 8: Modular invariance and Cardy growth

### Problem 8.1: Cardy formula from modular invariance

For a unitary compact 2D CFT with central charge $c$ and discrete spectrum, the torus partition function is

$$
Z(\tau,\bar\tau)=\mathrm{Tr}\,q^{L_0-c/24}\bar q^{\bar L_0-c/24},
\qquad
q=e^{2\pi i\tau}.
$$

Take a rectangular torus with $\tau=i\beta/(2\pi)$. Use modular invariance to derive the asymptotic density of high-energy states,

$$
S(E)\sim 2\pi\sqrt{\frac{c_{\mathrm{eff}}E}{3}},
$$

where $E=L_0+\bar L_0-c/12$ and $c_{\mathrm{eff}}$ is the effective central charge. State the simplification for a unitary CFT with vacuum dimension zero.

<details><summary><strong>Solution</strong></summary>

For a rectangular torus,

$$
Z(\beta)=\mathrm{Tr}\,e^{-\beta E},
\qquad
E=L_0+\bar L_0-\frac{c}{12}.
$$

Modular $S$ invariance relates the low-temperature and high-temperature limits:

$$
Z(\beta)=Z\left(\frac{4\pi^2}{\beta}\right).
$$

At low temperature, the partition function is dominated by the state of lowest shifted energy. Let

$$
E_0=-\frac{c_{\mathrm{eff}}}{12}.
$$

Then for large $4\pi^2/\beta$,

$$
Z\left(\frac{4\pi^2}{\beta}\right)
\sim
\exp\left(\frac{4\pi^2}{\beta}\frac{c_{\mathrm{eff}}}{12}\right)
=
\exp\left(\frac{\pi^2c_{\mathrm{eff}}}{3\beta}\right).
$$

Thus the high-temperature canonical free energy is controlled by

$$
\log Z(\beta)\sim \frac{\pi^2c_{\mathrm{eff}}}{3\beta}.
$$

The microcanonical density $\rho(E)$ follows by inverse Laplace transform:

$$
\rho(E)\sim \int d\beta\,\exp\left(\beta E+\frac{\pi^2c_{\mathrm{eff}}}{3\beta}\right).
$$

The saddle satisfies

$$
E=\frac{\pi^2c_{\mathrm{eff}}}{3\beta^2},
\qquad
\beta_*=\pi\sqrt{\frac{c_{\mathrm{eff}}}{3E}}.
$$

The saddle exponent is

$$
S(E)=\beta_*E+\frac{\pi^2c_{\mathrm{eff}}}{3\beta_*}
=2\pi\sqrt{\frac{c_{\mathrm{eff}}E}{3}}.
$$

For a unitary compact CFT with vacuum dimension zero,

$$
c_{\mathrm{eff}}=c.
$$

For independent left- and right-moving energies, the more refined formula is

$$
S\sim 2\pi\sqrt{\frac{c}{6}\left(L_0-\frac{c}{24}\right)}
+2\pi\sqrt{\frac{\bar c}{6}\left(\bar L_0-\frac{\bar c}{24}\right)}.
$$

This is the CFT side of the BTZ black-hole entropy match.

</details>

### Problem 8.2: Why modular invariance is not crossing symmetry

Both crossing symmetry and modular invariance are consistency conditions. Explain the difference between them.

<details><summary><strong>Solution</strong></summary>

Crossing symmetry is associativity of the local operator algebra. It compares different OPE decompositions of the same correlation function, for example the $s$- and $t$-channel decompositions of a four-point function on the sphere:

$$
(12)(34)\quad \text{versus}\quad (14)(23).
$$

Modular invariance is consistency under large diffeomorphisms of a higher-genus Euclidean spacetime, most famously the torus:

$$
\tau\mapsto \frac{a\tau+b}{c\tau+d},
\qquad
\begin{pmatrix}a&b\\c&d\end{pmatrix}\in SL(2,\mathbb Z).
$$

It constrains the spectrum and Hilbert-space trace

$$
Z(\tau,\bar\tau)=\mathrm{Tr}_{\mathcal H}\,q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}.
$$

So:

| Constraint | Object | Physical meaning |
|---|---|---|
| crossing | local correlators | OPE associativity |
| modular invariance | partition functions and higher-genus amplitudes | consistency of quantization on nontrivial manifolds |

In rational 2D CFT the two are deeply related through chiral algebras, fusion, and modular tensor categories, but they are not the same statement.

</details>

## Problem Set 9: Thermal CFT and entanglement

### Problem 9.1: Conformal equation of state

For a homogeneous thermal CFT in flat $d$-dimensional spacetime, show that

$$
\epsilon=(d-1)p,
$$

where $\epsilon$ is the energy density and $p$ is the pressure. Then show that

$$
p\propto T^d,
\qquad
s\propto T^{d-1}.
$$

<details><summary><strong>Solution</strong></summary>

For a homogeneous isotropic thermal state,

$$
\langle T^\mu{}_{\nu}\rangle
=\mathrm{diag}(-\epsilon,p,p,\ldots,p)
$$

in Lorentzian signature. Conformal invariance implies the stress tensor is traceless, up to anomalies. In flat space at finite temperature there is no curvature anomaly, so

$$
\langle T^\mu{}_{\mu}\rangle=-\epsilon+(d-1)p=0.
$$

Hence

$$
\epsilon=(d-1)p.
$$

Dimensional analysis gives the free energy density

$$
f(T)=-a_d T^d,
$$

where $a_d$ is theory-dependent. Since $p=-f$,

$$
p=a_dT^d.
$$

The entropy density is

$$
s=\frac{\partial p}{\partial T}=d a_d T^{d-1}.
$$

This scaling is the CFT side of the planar AdS black-brane thermodynamics.

</details>

### Problem 9.2: First law of entanglement for a ball

For the vacuum state of a CFT, the modular Hamiltonian of a ball $B$ of radius $R$ centered at the origin is

$$
K_B=2\pi\int_{|\vec x|<R} d^{d-1}x\,\frac{R^2-|\vec x|^2}{2R}T_{00}(0,\vec x).
$$

Use the entanglement first law

$$
\delta S_B=\delta\langle K_B\rangle
$$

to compute the first-order change in entanglement entropy for a homogeneous small energy-density perturbation $\delta\langle T_{00}\rangle=\delta\epsilon$.

<details><summary><strong>Solution</strong></summary>

Substitute the constant perturbation into $\delta\langle K_B\rangle$:

$$
\delta S_B
=2\pi\delta\epsilon
\int_{|\vec x|<R} d^{d-1}x\,\frac{R^2-r^2}{2R}.
$$

Let $n=d-1$ be the number of spatial dimensions. The volume element is

$$
d^n x=S_{n-1}r^{n-1}dr,
$$

so

$$
\int_{r<R} d^n x\,(R^2-r^2)
=S_{n-1}\int_0^R dr\,r^{n-1}(R^2-r^2).
$$

Compute

$$
\int_0^R dr\,r^{n-1}(R^2-r^2)
=\frac{R^{n+2}}{n}-\frac{R^{n+2}}{n+2}
=\frac{2R^{n+2}}{n(n+2)}.
$$

Thus

$$
\delta S_B
=2\pi\delta\epsilon\frac{1}{2R}
S_{n-1}\frac{2R^{n+2}}{n(n+2)}.
$$

Using $n=d-1$,

$$
\boxed{
\delta S_B
=\frac{2\pi S_{d-2}R^d}{(d-1)(d+1)}\,\delta\epsilon
}.
$$

This result is a key CFT input in the derivation of linearized Einstein equations from entanglement equilibrium.

</details>

## Problem Set 10: Supersymmetry and protected data

### Problem 10.1: BPS shortening as a norm condition

Suppose a superconformal primary $|\mathcal O\rangle$ obeys a schematic anticommutator

$$
\{S,Q\}=\Delta-R,
$$

on the relevant component of the multiplet. Show that unitarity implies

$$
\Delta\ge R,
$$

and that saturation implies shortening.

<details><summary><strong>Solution</strong></summary>

In radial quantization, $S$ is the adjoint of $Q$:

$$
Q^\dagger=S.
$$

Therefore

$$
\|Q|\mathcal O\rangle\|^2
=\langle \mathcal O|S Q|\mathcal O\rangle.
$$

If $|\mathcal O\rangle$ is annihilated by $S$, then on this primary state

$$
\langle \mathcal O|S Q|\mathcal O\rangle
=
\langle \mathcal O|\{S,Q\}|\mathcal O\rangle.
$$

Using the schematic algebra,

$$
\|Q|\mathcal O\rangle\|^2
=(\Delta-R)\langle \mathcal O|\mathcal O\rangle.
$$

Unitarity requires the norm to be nonnegative, so

$$
\Delta\ge R.
$$

If $\Delta=R$, then

$$
\|Q|\mathcal O\rangle\|^2=0.
$$

The descendant $Q|\mathcal O\rangle$ is null and is removed from the physical Hilbert space. The multiplet is shorter than a generic long multiplet. This is the algebraic meaning of BPS protection.

</details>

### Problem 10.2: Half-BPS chiral primaries in $\mathcal N=4$ SYM

The six real scalars of $\mathcal N=4$ SYM transform in the vector representation of $SO(6)_R$. Define a null auxiliary vector $Y^I$ satisfying $Y\cdot Y=0$, and write

$$
\mathcal O_p(x,Y)=Y^{I_1}\cdots Y^{I_p}\mathrm{Tr}\left(\Phi^{I_1}\cdots\Phi^{I_p}\right)+\text{multi-trace/subtraction terms}.
$$

Explain why the null condition packages the symmetric traceless representation $[0,p,0]$ of $SU(4)_R$, and state the protected dimension.

<details><summary><strong>Solution</strong></summary>

The product $Y^{I_1}\cdots Y^{I_p}$ is manifestly symmetric in the $SO(6)$ indices. Traces are encoded by contractions with $\delta_{IJ}$. Since

$$
Y\cdot Y=\delta_{IJ}Y^IY^J=0,
$$

any trace part vanishes when contracted with the null polarization vector. Thus $\mathcal O_p(x,Y)$ packages the symmetric traceless rank-$p$ representation of $SO(6)_R$.

Using

$$
SO(6)_R\simeq SU(4)_R,
$$

this representation has Dynkin label

$$
[0,p,0].
$$

The operator is half-BPS, so its dimension is protected:

$$
\Delta=p.
$$

In AdS/CFT, these operators are dual to Kaluza--Klein modes on $S^5$ with harmonic degree $p$.

</details>

## Problem Set 11: Large-$N$ CFT

### Problem 11.1: Connected correlator scaling

Let $\mathcal O_i$ be normalized single-trace operators in a large-$N$ gauge theory, with two-point functions of order one:

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle\sim O(N^0).
$$

Use planar counting to argue that connected $k$-point functions scale as

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c\sim N^{2-k}.
$$

Explain the AdS interpretation.

<details><summary><strong>Solution</strong></summary>

For adjoint matrix fields, vacuum ribbon diagrams scale as

$$
N^{2-2g},
$$

where $g$ is the genus. A single-trace insertion creates one boundary on the ribbon surface. A connected planar diagram with $k$ single-trace insertions therefore scales as

$$
N^{2-k}
$$

before accounting for normalization. Choosing operators normalized to have order-one two-point functions gives the stated scaling:

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_c\sim N^{2-k}.
$$

In particular,

$$
\langle \mathcal O\mathcal O\rangle_c\sim N^0,
$$

$$
\langle \mathcal O\mathcal O\mathcal O\rangle_c\sim \frac{1}{N},
$$

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_c\sim \frac{1}{N^2}.
$$

The AdS interpretation is that $1/N$ is a bulk interaction strength. More precisely, in standard large-$N$ holographic theories,

$$
G_N^{\mathrm{bulk}}\sim \frac{1}{N^2}.
$$

Thus large-$N$ factorization corresponds to the classical bulk limit. Connected correlators are suppressed because bulk quantum fluctuations are suppressed.

</details>

### Problem 11.2: Large-$N$ anomalous dimensions from logarithms

Suppose a four-point function has a conformal block expansion containing double-trace operators with dimensions

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\frac{1}{N^2}\gamma_{n,\ell}+O(N^{-4}).
$$

Show why expanding the blocks produces terms proportional to

$$
\frac{1}{N^2}\gamma_{n,\ell}\log u.
$$

<details><summary><strong>Solution</strong></summary>

In the small-$u$ limit, a conformal block behaves schematically as

$$
G_{\Delta,\ell}(u,v)\sim u^{\Delta/2}\times \text{function of }v.
$$

Substitute

$$
\Delta=\Delta^{(0)}+\frac{1}{N^2}\gamma+O(N^{-4}).
$$

Then

$$
 u^{\Delta/2}
 =u^{\Delta^{(0)}/2}
 u^{\gamma/(2N^2)}
 =u^{\Delta^{(0)}/2}
 \left(1+\frac{\gamma}{2N^2}\log u+O(N^{-4})\right).
$$

Therefore anomalous dimensions appear in the four-point function as logarithmic terms:

$$
\frac{1}{N^2}\gamma_{n,\ell}\log u.
$$

In AdS, these logarithms encode shifts in two-particle energies caused by weak bulk interactions.

</details>

## Problem Set 12: The pre-AdS/CFT dictionary

### Problem 12.1: Scalar mass-dimension relation

A scalar field in Euclidean $\mathrm{AdS}_{d+1}$ with radius $L$ obeys

$$
(\nabla^2-m^2)\phi=0.
$$

Near the boundary in Poincare coordinates,

$$
ds^2=L^2\frac{dz^2+dx^\mu dx_\mu}{z^2},
\qquad
z\to 0,
$$

assume

$$
\phi(z,x)\sim z^\alpha \phi_0(x).
$$

Show that

$$
m^2L^2=\alpha(\alpha-d).
$$

Therefore the two possible exponents are

$$
\alpha=\Delta,
\qquad
\alpha=d-\Delta,
$$

where

$$
m^2L^2=\Delta(\Delta-d).
$$

<details><summary><strong>Solution</strong></summary>

Near the boundary, neglect $x$-derivatives relative to radial scaling. The scalar Laplacian in $\mathrm{AdS}_{d+1}$ gives

$$
\nabla^2\phi
\sim
\frac{1}{L^2}z^{d+1}\partial_z\left(z^{1-d}\partial_z\phi\right).
$$

For $\phi=z^\alpha\phi_0(x)$,

$$
\partial_z\phi=\alpha z^{\alpha-1}\phi_0,
$$

and

$$
z^{1-d}\partial_z\phi
=\alpha z^{\alpha-d}\phi_0.
$$

Then

$$
\partial_z\left(z^{1-d}\partial_z\phi\right)
=\alpha(\alpha-d)z^{\alpha-d-1}\phi_0.
$$

Multiplying by $z^{d+1}/L^2$ gives

$$
\nabla^2\phi
\sim
\frac{\alpha(\alpha-d)}{L^2}z^\alpha\phi_0.
$$

The wave equation becomes

$$
\frac{\alpha(\alpha-d)}{L^2}z^\alpha\phi_0-m^2z^\alpha\phi_0=0,
$$

so

$$
m^2L^2=\alpha(\alpha-d).
$$

Writing one root as $\Delta$, the other is $d-\Delta$, and

$$
m^2L^2=\Delta(\Delta-d).
$$

The boundary source and response are associated with the two independent asymptotic coefficients.

</details>

### Problem 12.2: CFT data as bulk data

Explain how the following CFT data appear in a weakly coupled AdS dual:

| CFT datum | Bulk interpretation |
|---|---|
| scalar primary dimension $\Delta$ | ? |
| spin-$\ell$ primary | ? |
| conserved current $J_\mu$ | ? |
| stress tensor $T_{\mu\nu}$ | ? |
| OPE coefficient $C_{ijk}$ | ? |
| large central charge $C_T$ | ? |

<details><summary><strong>Solution</strong></summary>

The dictionary is:

| CFT datum | Bulk interpretation |
|---|---|
| scalar primary dimension $\Delta$ | mass of a bulk scalar, $m^2L^2=\Delta(\Delta-d)$ |
| spin-$\ell$ primary | bulk spin-$\ell$ field or composite multi-particle state |
| conserved current $J_\mu$ | bulk gauge field $A_M$ |
| stress tensor $T_{\mu\nu}$ | bulk metric fluctuation $g_{MN}$, i.e. the graviton |
| OPE coefficient $C_{ijk}$ | cubic bulk coupling, after normalization |
| large central charge $C_T$ | small Newton constant, $C_T\sim L^{d-1}/G_N$ |

The point is that CFT data are not merely boundary observables. They are the nonperturbative definition of the bulk theory. Weakly coupled Einstein gravity is a special regime of CFT data: large $C_T$, sparse low-spin single-trace spectrum, large-$N$ factorization, and controlled anomalous dimensions.

</details>

## Mini-projects

Each mini-project should result in a short note of 5--10 pages, or an equivalent webpage. A good project has a clear question, a derivation, one explicit example, and an AdS/CFT checkpoint.

### Project A: A toy numerical bootstrap

Build a simple numerical bootstrap for identical scalar four-point functions in one dimension or for a truncated higher-dimensional crossing equation.

Deliverables:

1. Derive the crossing equation.
2. Choose a finite derivative basis at the crossing-symmetric point.
3. Implement a linear-functional search.
4. Plot one exclusion curve or demonstrate one allowed/disallowed spectrum.
5. Explain which ingredients survive in the full modern bootstrap.

### Project B: The Ising model as CFT data

Write a note explaining how the critical Ising model is encoded by CFT data.

Minimum content:

$$
\sigma\times\sigma=1+\epsilon+\cdots,
$$

critical exponents from $\Delta_\sigma$ and $\Delta_\epsilon$, and the difference between the exact 2D solution and the numerical 3D bootstrap logic.

### Project C: Virasoro minimal models from null vectors

Starting from a level-two null state, derive the BPZ differential equation for a four-point function containing a degenerate primary. Then apply the result to one Ising-model correlator.

A strong project also explains why the existence of null states converts symmetry into solvability.

### Project D: Modular invariance and black-hole entropy

Derive the Cardy formula carefully and compare it with the BTZ entropy. The final section should identify which assumptions enter the Cardy derivation and which assumptions enter the gravity derivation.

### Project E: Generalized free fields and two-particle AdS states

Use generalized free four-point functions to identify double-trace towers. Explain the interpretation of $n$ and $\ell$ as radial and angular quantum numbers in global AdS.

A strong project computes at least one explicit low-lying OPE coefficient from mean-field theory.

### Project F: Large-spin perturbation theory and bulk locality

Explain why the crossed-channel identity contribution implies large-spin double-twist operators. Then discuss how anomalous dimensions at large spin encode long-distance bulk forces.

### Project G: The ball modular Hamiltonian and linearized gravity

Starting from

$$
K_B=2\pi\int_B d^{d-1}x\,\frac{R^2-r^2}{2R}T_{00},
$$

explain how the entanglement first law maps to the first law of hyperbolic black holes or to the linearized gravitational equations in AdS.

### Project H: $\mathcal N=4$ chiral primaries and $S^5$ harmonics

Explain the map

$$
[0,p,0],\quad \Delta=p
\quad\longleftrightarrow\quad
S^5\text{ scalar harmonic of degree }p.
$$

Include the mass-dimension relation

$$
m^2L^2=p(p-4)
$$

for the corresponding scalar in $\mathrm{AdS}_5$.

### Project I: Wilson loops and defect CFT

Study the half-BPS Wilson line in $\mathcal N=4$ SYM as a one-dimensional defect CFT. Identify the preserved symmetry, define defect operators, and explain the displacement operator.

### Project J: From this course to AdS/CFT proper

Write a “pre-dictionary” memo: choose ten equations from this CFT course and explain exactly where each enters the AdS/CFT correspondence.

The memo should include at least:

$$
Z_{\mathrm{CFT}}[J]=Z_{\mathrm{bulk}}[\phi_\partial=J],
$$

$$
m^2L^2=\Delta(\Delta-d),
$$

$$
C_T\sim \frac{L^{d-1}}{G_N},
$$

and large-$N$ factorization.

## Capstone checklist

A student is ready to begin a serious AdS/CFT course when the following tasks feel routine:

1. Derive scalar two- and three-point functions from conformal symmetry.
2. Explain the difference between source, vev, and operator.
3. Use radial quantization to translate dimensions into energies.
4. State and use unitarity bounds.
5. Write an OPE and a conformal block decomposition.
6. Derive the identical-scalar crossing equation.
7. Explain why large-$N$ factorization means weak bulk coupling.
8. Identify single-trace and multi-trace operators.
9. Explain the role of $T_{\mu\nu}$, $J_\mu$, and scalar primaries in the bulk dictionary.
10. Recognize which parts of 2D CFT are special to Virasoro symmetry and which parts generalize to higher dimensions.

The highest-level synthesis is this:

$$
\boxed{
\text{AdS/CFT is not a map from a Lagrangian to a spacetime; it is a map from consistent CFT data to quantum gravity in AdS.}
}
$$

The problem sets above are designed to make that sentence operational.
