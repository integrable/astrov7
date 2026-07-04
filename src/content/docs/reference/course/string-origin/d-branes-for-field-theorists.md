---
title: "D-Branes for Field Theorists"
description: "A field-theorist's guide to D-branes as open-string boundary conditions, worldvolume gauge theories, and charged sources for closed-string fields."
sidebar:
  order: 20
---

The previous page introduced the minimal string-theory fact behind AdS/CFT:

$$
\text{open strings give gauge fields},
\qquad
\text{closed strings give gravity}.
$$

D-branes are the objects that let both statements act on the same physical system. An open string can end on a D-brane; therefore a D-brane supports open-string degrees of freedom. A D-brane also has tension and Ramond–Ramond charge; therefore it sources closed-string fields, including the metric. This double life is the seed of the D3-brane derivation of AdS/CFT.

This page explains D-branes in a language useful to a field theorist. The point is not to quantize the superstring from scratch. The point is to understand why a stack of D-branes naturally carries a gauge theory, why its scalar fields describe positions in transverse space, and why the same stack can be replaced, at strong backreaction, by a gravitational geometry.

The page after this one will specialize to D3-branes and compare their two low-energy descriptions. Here we build the vocabulary needed for that comparison.

## Why this matters

A D-brane is simultaneously three things:

1. an allowed boundary condition for open strings;
2. a dynamical object whose worldvolume supports a quantum field theory;
3. a charged source for closed-string supergravity fields.

For AdS/CFT, the crucial object is a stack of $N$ coincident D3-branes. Its open-string description gives a four-dimensional gauge theory with gauge group $U(N)$, or effectively $SU(N)$ after the decoupled center-of-mass $U(1)$ is separated. Its closed-string description gives a ten-dimensional gravitational solution. The canonical duality arises by taking a low-energy limit in which these two descriptions become two ways of describing the same degrees of freedom.

<figure class="doc-figure" style="--figure-width: 58rem;">

![D-branes as boundary conditions, worldvolume field theories, and closed-string sources](/figures/course/d-branes-field-theorists.svg)

<figcaption>

A D$p$-brane is an open-string boundary condition, a $(p+1)$-dimensional worldvolume field theory, and a source for closed-string fields. Open-string endpoints obey Neumann conditions along the brane and Dirichlet conditions transverse to it. For $N$ coincident branes, the massless open strings give a $U(N)$ gauge theory with adjoint fields. The same branes have tension and Ramond–Ramond charge, so they backreact on the surrounding closed-string fields.

</figcaption>
</figure>

## The operational definition

Work in ten-dimensional type II string theory, with coordinates

$$
X^M,
\qquad
M=0,1,\ldots,9.
$$

A D$p$-brane is an object extended in $p$ spatial directions and time. Its worldvolume has dimension $p+1$. Split the spacetime coordinates into directions parallel and transverse to the brane:

$$
X^a,
\qquad
 a=0,1,\ldots,p,
$$

and

$$
X^i,
\qquad
 i=p+1,\ldots,9.
$$

For an open string ending on a flat static D$p$-brane at transverse position $y^i$, the endpoint is free to move along the brane but fixed in the transverse directions. The corresponding boundary conditions are

$$
\partial_\sigma X^a\big|_{\partial\Sigma}=0,
\qquad
X^i\big|_{\partial\Sigma}=y^i.
$$

The first condition is Neumann. The second is Dirichlet. The letter “D” in D-brane means Dirichlet.

One way to see these conditions is to vary the string action. For the bosonic part of the worldsheet action in flat space,

$$
S_{\rm ws}
=
-\frac{1}{4\pi\alpha'}
\int d\tau d\sigma\,
\eta_{MN}\partial_\alpha X^M\partial^\alpha X^N,
$$

the variation produces a boundary term of the schematic form

$$
\delta S_{\rm ws}\big|_{\partial\Sigma}
=
-\frac{1}{2\pi\alpha'}
\int_{\partial\Sigma}d\tau\,
\delta X_M\partial_\sigma X^M .
$$

This vanishes in either of two ways:

$$
\partial_\sigma X^M=0
\qquad
\text{or}
\qquad
\delta X^M=0.
$$

Neumann directions use the first option. Dirichlet directions use the second. A D$p$-brane is a mixed boundary condition: Neumann in $p+1$ worldvolume directions, Dirichlet in $9-p$ transverse directions.

This definition sounds kinematical, but it has dynamical consequences. Once open strings can end on such a hypersurface, their endpoint excitations become fields living on that hypersurface.


## Which D-branes exist?

In type II string theory, supersymmetric D-branes come in two families. Type IIA contains BPS D$p$-branes with even $p$, while type IIB contains BPS D$p$-branes with odd $p$:

$$
\begin{array}{ccl}
\text{type IIA} &:& p=0,2,4,6,8,\\
\text{type IIB} &:& p=-1,1,3,5,7,9.
\end{array}
$$

The D$(-1)$-brane is an instantonic object localized in spacetime. The D9-brane fills all spatial directions of type IIB. The foundational AdS$_5$/CFT$_4$ example uses D3-branes, so it lives naturally in type IIB string theory.

For this course, the most important point is not the full classification. It is that the value of $p$ fixes both the dimension of the worldvolume gauge theory and the kind of Ramond–Ramond potential sourced by the brane:

$$
\text{D}p\text{-brane}
\quad
\Rightarrow
\quad
(p+1)\text{-dimensional QFT and coupling to }C_{p+1}.
$$

## The brane worldvolume is a spacetime for a QFT

A D$p$-brane has a $(p+1)$-dimensional worldvolume, which we can parameterize by coordinates

$$
\xi^a,
\qquad a=0,1,\ldots,p.
$$

In static gauge, one identifies

$$
X^a(\xi)=\xi^a.
$$

The transverse position of the brane is then described by functions

$$
X^i(\xi)=Y^i(\xi),
\qquad
 i=p+1,\ldots,9.
$$

From the worldvolume point of view, the $Y^i$ are scalar fields. Thus a brane is not merely a rigid submanifold. It can fluctuate, and its transverse fluctuations are fields on the brane.

It is often useful to rescale the transverse position into a field with canonical gauge-theory dimensions:

$$
\Phi^i
\sim
\frac{Y^i}{2\pi\alpha'}.
$$

The exact normalization depends on conventions, but the physical idea is invariant:

$$
\text{worldvolume scalar field}
\quad
\longleftrightarrow
\quad
\text{transverse position of the brane}.
$$

This is one of the first places where geometry becomes a field in a gauge theory. Later, for D3-branes, the six transverse scalars of $\mathcal N=4$ super-Yang–Mills will be precisely this kind of brane-position field.

## The gauge field from open strings

There is a direct worldsheet way to see why a gauge field belongs on the brane. An open-string endpoint can couple to a worldvolume one-form $A=A_a dX^a$ through a boundary term

$$
S_{\partial\Sigma}
=
\int_{\partial\Sigma} A_a(X)\,dX^a.
$$

Under a gauge transformation

$$
A\longrightarrow A+d\Lambda,
$$

the boundary action changes by endpoint terms. For a closed boundary component this is harmless, and in the quantum theory it is precisely the usual gauge redundancy. Thus the open-string endpoint naturally sees a gauge potential living along the brane.

For a stack of branes, the endpoint labels are matrix indices, so the boundary coupling becomes non-Abelian. In that case the open-string endpoint effectively carries a Wilson line:

$$
\operatorname{Tr}\,P\exp\!\left(\int_{\partial\Sigma} A_a(X)\,dX^a\right),
$$

where $P$ denotes path ordering. This is the worldsheet ancestor of Wilson loops in the brane gauge theory, and later of fundamental strings ending on boundary Wilson loops in AdS/CFT.

The same physics appears in the massless spectrum. An open superstring ending on a D$p$-brane contains a vector field along the brane:

$$
A_a(\xi),
\qquad a=0,1,\ldots,p.
$$

It is a gauge field on the worldvolume. For a single isolated D-brane, the gauge group is $U(1)$. The brane also has transverse scalar fields $\Phi^i$, plus fermions required by supersymmetry. For a flat D$p$-brane in type II string theory, the low-energy worldvolume theory is the dimensional reduction of ten-dimensional maximally supersymmetric Yang–Mills theory down to $p+1$ dimensions.

A quick way to remember the field content is:

$$
\begin{array}{ccl}
\text{ten-dimensional gauge field } A_M
&\longrightarrow&
A_a \;\text{on the brane},\\
&&
\Phi^i \equiv A_i \;\text{as transverse scalars}.
\end{array}
$$

This formula is not saying that the transverse coordinates are literally gauge-field components in spacetime. It is saying that the worldvolume multiplet is obtained by dimensional reduction: components of a higher-dimensional gauge field along directions that the fields do not depend on become scalars in the lower-dimensional theory.

The number of transverse scalars is

$$
9-p.
$$

For $p=3$, this gives six scalar fields, matching the six scalar fields of four-dimensional $\mathcal N=4$ SYM.

## Stacks and matrix fields

Now place $N$ identical D$p$-branes on top of each other. An oriented open string can begin on brane $i$ and end on brane $j$:

$$
i,j=1,\ldots,N.
$$

The endpoint labels are called Chan–Paton labels. A massless open-string field therefore carries two brane labels:

$$
A_a(\xi)^i{}_j,
\qquad
\Phi^k(\xi)^i{}_j.
$$

That is exactly the index structure of an $N\times N$ matrix. The massless fields on $N$ coincident branes are matrix-valued and transform in the adjoint representation of $U(N)$.

The emergence of non-Abelian gauge theory is one of the most important lessons of D-branes:

$$
N\;\text{coincident D-branes}
\quad
\Longrightarrow
\quad
U(N)\;\text{worldvolume gauge theory}.
$$

For AdS/CFT, this is the origin of the rank $N$ in $\mathcal N=4$ super-Yang–Mills.

There is a small but important caveat. The gauge group for $N$ coincident branes is naturally $U(N)$, not $SU(N)$. The overall $U(1)$ describes the center-of-mass motion of the brane stack and usually decouples from the interacting large-$N$ sector. In much of AdS/CFT one focuses on the $SU(N)$ part because it carries the interacting single-trace dynamics.

## Separated branes and the Higgs mechanism

Suppose the branes are not coincident. Let the $i$-th brane sit at transverse position $y_i^k$. A string stretching from brane $i$ to brane $j$ has a minimum length

$$
|y_i-y_j|.
$$

Its classical energy is tension times length:

$$
m_{ij}
\simeq
\frac{|y_i-y_j|}{2\pi\alpha'}.
$$

Thus the off-diagonal open strings become massive when the branes are separated. In the worldvolume gauge theory, this is the Higgs mechanism. A diagonal expectation value for the matrix scalar

$$
\Phi^k
=
\operatorname{diag}(\phi_1^k,\ldots,\phi_N^k)
$$

breaks

$$
U(N)
\longrightarrow
U(1)^N,
$$

and the off-diagonal gauge bosons acquire masses proportional to

$$
|\phi_i-\phi_j|.
$$

The geometric and field-theory interpretations are the same statement:

$$
\text{brane separation}
\quad
\longleftrightarrow
\quad
\text{scalar expectation value}.
$$

This is a useful sanity check. A stack of coincident branes has enhanced non-Abelian gauge symmetry because the strings connecting different branes can become massless. Separating the branes makes those connecting strings heavy and breaks the symmetry.

## The low-energy worldvolume theory

At energies much smaller than the string scale,

$$
E \ll \ell_s^{-1},
\qquad
\ell_s=\sqrt{\alpha'},
$$

massive string excitations decouple. The remaining open-string modes give a local quantum field theory on the D-brane worldvolume. For a flat stack of $N$ D$p$-branes, the leading two-derivative action is maximally supersymmetric Yang–Mills theory in $p+1$ dimensions:

$$
S_{\rm SYM}
=
\frac{1}{g_{{\rm YM},p+1}^2}
\int d^{p+1}x\,\operatorname{Tr}
\left[
-\frac14 F_{ab}F^{ab}
-\frac12 D_a\Phi^i D^a\Phi^i
+\frac14[\Phi^i,\Phi^j]^2
+\text{fermions}
\right].
$$

The commutator potential has an important geometric meaning. If all the scalar matrices commute, they can be diagonalized simultaneously. Their eigenvalues describe the positions of the individual branes. If the matrices do not commute, the configuration is not describable as a simple set of separated classical branes. The noncommuting matrix degrees of freedom are genuinely stringy, and they are one reason D-branes became central to nonperturbative string theory.

The worldvolume gauge coupling scales as

$$
g_{{\rm YM},p+1}^2
\sim
 g_s(\alpha')^{(p-3)/2},
$$

up to convention-dependent powers of $2\pi$. Its mass dimension is

$$
[g_{{\rm YM},p+1}^2]=3-p.
$$

This dimensional analysis already singles out $p=3$:

$$
[g_{{\rm YM},4}^2]=0.
$$

A D3-brane worldvolume gauge coupling is dimensionless, as required for a four-dimensional conformal gauge theory. This is not yet the full proof of conformality, but it is the first hint that D3-branes are special.

## The DBI action

The Yang–Mills action is the leading low-energy approximation. A more geometric action for a single D-brane is the Dirac–Born–Infeld action:

$$
S_{\rm DBI}
=
-\tau_p
\int_{\Sigma_{p+1}} d^{p+1}\xi\,
e^{-\Phi_{\rm dil}}
\sqrt{-\det\left(
P[G+B]_{ab}+2\pi\alpha' F_{ab}
\right)} .
$$

Here:

- $\Sigma_{p+1}$ is the brane worldvolume;
- $P[G+B]_{ab}$ is the pullback of the spacetime metric and NS–NS two-form to the brane;
- $F_{ab}$ is the worldvolume gauge-field strength;
- $\Phi_{\rm dil}$ is the spacetime dilaton;
- $\tau_p$ is a conventional normalization independent of the asymptotic value of $g_s$.

A common type II normalization is

$$
\tau_p
=
\frac{1}{(2\pi)^p\alpha'^{(p+1)/2}}.
$$

With constant dilaton $e^{\Phi_{\rm dil}}=g_s$, the physical tension is

$$
T_p^{\rm phys}
=
\tau_p e^{-\Phi_{\rm dil}}
=
\frac{1}{(2\pi)^p g_s\alpha'^{(p+1)/2}}.
$$

This $1/g_s$ scaling tells us that D-branes are nonperturbative objects from the closed-string point of view. They are heavy at weak string coupling, but open strings can still end on them and produce a useful perturbative description.

To recover Yang–Mills theory, expand the determinant in powers of $F$ and derivatives of the transverse fluctuations. For small fields in flat space,

$$
\sqrt{-\det(\eta_{ab}+2\pi\alpha' F_{ab})}
=
1+
\frac{(2\pi\alpha')^2}{4}F_{ab}F^{ab}
+\cdots .
$$

The constant term gives the brane tension. The quadratic term gives the Maxwell or Yang–Mills kinetic term. For a stack of branes the full non-Abelian DBI action is subtle beyond the leading low-energy terms, but the leading supersymmetric Yang–Mills theory is robust.

## The Wess–Zumino coupling and Ramond–Ramond charge

A D-brane is not only tense. It is charged under Ramond–Ramond gauge potentials. A D$p$-brane couples electrically to a $(p+1)$-form potential

$$
C_{p+1}.
$$

The corresponding Wess–Zumino coupling is schematically

$$
S_{\rm WZ}
=
\mu_p
\int_{\Sigma_{p+1}}
P\!\left[\sum_q C_q\right]\wedge e^{B+2\pi\alpha' F}.
$$

The simplest term is

$$
\mu_p\int_{\Sigma_{p+1}} P[C_{p+1}],
$$

which says that the D$p$-brane carries electric charge under $C_{p+1}$. Expanding the exponential also gives terms such as

$$
\mu_p(2\pi\alpha')
\int_{\Sigma_{p+1}} P[C_{p-1}]\wedge F.
$$

Since a D$(p-2)$-brane couples electrically to $C_{p-1}$, this term means that worldvolume gauge flux on a D$p$-brane can carry lower-dimensional D-brane charge. This is one reason the gauge field on a brane is not an optional decoration; it is part of the brane's charge data.

This is the closed-string side of the D-brane story. The same object that supports an open-string gauge theory also acts as a source for supergravity fields. In particular, it sources:

$$
\text{metric},
\qquad
\text{dilaton},
\qquad
\text{Ramond–Ramond fields}.
$$

For many coincident branes, the source is proportional to $N$. The parameter controlling the strength of the resulting backreaction is roughly

$$
g_s N.
$$

This is why D-branes have two complementary descriptions:

$$
g_s N\ll 1
\quad
\Rightarrow
\quad
\text{weakly backreacting branes with open-string gauge theory},
$$

while

$$
g_s N\gg 1
\quad
\Rightarrow
\quad
\text{strongly backreacted geometry described by supergravity, if curvature is small}.
$$

For D3-branes, $g_sN$ is proportional to the boundary 't Hooft coupling, up to a convention-dependent numerical factor. The next pages will make this statement precise.

The schematic extremal D$p$-brane metric in string frame is

$$
ds^2_{\rm str}
=
H_p(r)^{-1/2}\eta_{ab}dx^a dx^b
+
H_p(r)^{1/2}\left(dr^2+r^2d\Omega_{8-p}^2\right),
$$

with a dilaton profile

$$
e^{\Phi_{\rm dil}}
=
g_s H_p(r)^{(3-p)/4}.
$$

For $p<7$, the harmonic function has the form

$$
H_p(r)=1+\frac{L_p^{7-p}}{r^{7-p}},
$$

where, up to numerical constants,

$$
L_p^{7-p}\sim g_sN\alpha'^{(7-p)/2}.
$$

This geometry is the closed-string answer to the same question that the open-string calculation answers by giving a $U(N)$ gauge theory. The parameter $N$ is matrix size on one side and brane charge or flux on the other.

## BPS balance and why the two views can agree

D-branes in type II string theory can preserve part of the spacetime supersymmetry. Such branes are called BPS branes. BPS objects have a special relation between their mass and charge. Very schematically,

$$
\text{tension}
=
\text{charge}
$$

in suitable units.

This equality has a concrete force-balance consequence. Two parallel identical BPS D-branes exert no net static force on each other. The attractive exchange of NS–NS fields, including the graviton and dilaton, cancels the repulsive exchange of Ramond–Ramond fields.

This cancellation matters because it makes a stack of coincident branes stable and controlled. It also protects many quantities as one changes $g_sN$. One can analyze the same brane system in a weakly backreacted open-string regime and in a strongly backreacted closed-string regime, then compare protected information between the two.

AdS/CFT goes much further than protected comparisons, but historically and structurally, this BPS control is part of what made the D3-brane argument sharp.

## Probe branes versus backreacted branes

There are two common approximations involving D-branes.

A **probe brane** is a brane whose own backreaction on the geometry is neglected. One studies its DBI and Wess–Zumino action in a fixed background. This is valid when the brane contributes only a small amount of energy or charge compared with the background.

A **backreacted brane** is included as a source in the supergravity equations. A stack of many branes can curve spacetime substantially. The D3-brane geometry used in the canonical AdS/CFT derivation is a backreacted solution.

The distinction is not merely technical. It corresponds to different physical questions:

$$
\text{probe brane}
\quad
\Rightarrow
\quad
\text{add a small sector to a large system},
$$

whereas

$$
\text{backreacted brane stack}
\quad
\Rightarrow
\quad
\text{replace the system by a new geometry}.
$$

Later, probe branes will be useful for adding flavor degrees of freedom in holography. But the foundational D3-brane derivation uses the backreacted geometry of the whole brane stack.

## D3-branes are the special case for AdS$_5$/CFT$_4$

For a D3-brane, the worldvolume is four-dimensional:

$$
p+1=4.
$$

The low-energy theory on $N$ coincident D3-branes is four-dimensional $\mathcal N=4$ super-Yang–Mills theory with gauge group $U(N)$. Its field content is:

$$
A_\mu,
\qquad
\Phi^I,
\qquad
\text{fermions},
$$

where

$$
\mu=0,1,2,3,
\qquad
I=1,\ldots,6.
$$

The six scalars describe fluctuations of the branes in the six transverse directions. Rotations of those transverse directions form

$$
SO(6)\simeq SU(4),
$$

which becomes the R-symmetry of $\mathcal N=4$ SYM.

The dimensionless four-dimensional coupling is related to the string coupling by a convention-dependent numerical factor. In the common AdS/CFT convention,

$$
g_{\rm YM}^2=4\pi g_s,
\qquad
\lambda=g_{\rm YM}^2N=4\pi g_s N.
$$

Some string perturbation theory conventions instead place a factor $2\pi$ in this relation. The important invariant statement is that

$$
\lambda \propto g_s N.
$$

This proportionality is the first bridge between the gauge-theory expansion and the gravitational backreaction of the brane stack.

## The same branes, two perturbation theories

The D-brane picture gives two expansions of the same underlying system.

On the open-string side, perturbation theory is organized by worldsheet diagrams with boundaries. Boundaries end on D-branes, and Chan–Paton labels lead to powers of $N$. This is the stringy origin of large-$N$ gauge theory.

On the closed-string side, the same branes are sources for gravitational fields. When $N$ is large and the backreaction is strong but weakly curved, the closed-string description can become classical supergravity.

For D3-branes, the two sides will become:

$$
\text{open-string low-energy theory on branes}
\quad
\longrightarrow
\quad
\mathcal N=4\;\text{SYM},
$$

and

$$
\text{closed-string near-horizon geometry of branes}
\quad
\longrightarrow
\quad
\mathrm{AdS}_5\times S^5.
$$

The next page is devoted to this double description.

## Dictionary checkpoint

The useful translations from this page are:

| D-brane language | Field-theory language |
|---|---|
| one D$p$-brane | one $U(1)$ worldvolume gauge theory |
| $N$ coincident D$p$-branes | $U(N)$ worldvolume gauge theory |
| open-string Chan–Paton labels | matrix indices of adjoint fields |
| transverse brane position $Y^i$ | scalar field expectation value $\Phi^i$ |
| separated branes | Higgsed gauge symmetry |
| strings between separated branes | massive off-diagonal fields |
| brane tension | coupling to the metric and dilaton |
| Ramond–Ramond charge | coupling to $C_{p+1}$ |
| strong backreaction of many branes | closed-string supergravity geometry |

For AdS/CFT, the most important line is:

$$
N\;\text{D3-branes}
\quad
\Longrightarrow
\quad
\mathcal N=4\;U(N)\;\text{SYM at low energy}.
$$

The gravitational side of the same line will be derived next.

## Common confusions

### “A D-brane is just a boundary of spacetime.”

No. A D-brane is not usually a boundary of the ten-dimensional spacetime. It is a dynamical object embedded in spacetime. Open-string worldsheets can have boundaries, and those boundaries lie on the D-brane.

### “Dirichlet means the brane cannot move.”

Dirichlet boundary conditions fix the endpoint of a given open string relative to the brane. The brane itself is dynamical. Its transverse position becomes a worldvolume scalar field.

### “The brane gauge theory lives in ten dimensions.”

No. The open-string gauge theory lives on the brane worldvolume, which has dimension $p+1$. For D3-branes, this is four-dimensional. The surrounding closed-string theory lives in ten dimensions.

### “The gauge group should be $SU(N)$ because AdS/CFT uses $SU(N)$.”

The open strings on $N$ coincident D-branes naturally give $U(N)$. The overall $U(1)$ describes center-of-mass degrees of freedom and decouples from the interacting large-$N$ sector. The interacting part is usually described as $SU(N)$.

### “DBI is the full non-Abelian D-brane action.”

For a single brane, the DBI plus Wess–Zumino action captures many low-energy effects. For multiple coincident branes, the complete non-Abelian action at all orders is subtle. The leading low-energy supersymmetric Yang–Mills action is the part needed for the foundational AdS/CFT argument.

### “Large $N$ automatically means classical gravity.”

Not by itself. Large $N$ helps suppress quantum loops, but the geometry must also be weakly curved in string units. For D3-branes, weak curvature requires large 't Hooft coupling. The classical Einstein gravity limit needs both large $N$ and large $\lambda$.

## Exercises

### Exercise 1: Dimensions of the D$p$-brane gauge coupling

In $p+1$ spacetime dimensions, the Yang–Mills action contains

$$
S\sim
\frac{1}{g_{{\rm YM},p+1}^2}
\int d^{p+1}x\, F_{ab}F^{ab}.
$$

Using $[S]=0$ and $[d^{p+1}x]=-(p+1)$ in mass units, show that

$$
[g_{{\rm YM},p+1}^2]=3-p.
$$

<details>
<summary><strong>Solution</strong></summary>

In $p+1$ dimensions, the Lagrangian density has mass dimension $p+1$. For a gauge field with canonical kinetic term, the field strength term contributes a factor whose coefficient has dimension

$$
\left[\frac{1}{g_{{\rm YM},p+1}^2}\right]=p-3.
$$

Equivalently,

$$
[g_{{\rm YM},p+1}^2]=3-p.
$$

Thus the Yang–Mills coupling is dimensionless only when $p=3$. This is one reason D3-branes are special: their low-energy worldvolume gauge coupling can be a conformal coupling rather than a relevant or irrelevant dimensionful parameter.

</details>

### Exercise 2: Mass of a stretched string

Two parallel D-branes are separated by a transverse distance $r$. Estimate the mass of the lightest open string stretching from one brane to the other.

<details>
<summary><strong>Solution</strong></summary>

The string has tension

$$
T_s=\frac{1}{2\pi\alpha'}.
$$

A string stretched a distance $r$ has classical energy

$$
E\simeq T_s r
=
\frac{r}{2\pi\alpha'}.
$$

This energy appears as a mass in the worldvolume theory:

$$
m\simeq \frac{r}{2\pi\alpha'}.
$$

When the branes coincide, $r\to0$, these off-diagonal strings can become massless. This is the string picture of enhanced gauge symmetry.

</details>

### Exercise 3: The first Yang–Mills term from DBI

Start from the single-brane DBI determinant in flat space with small gauge field:

$$
\sqrt{-\det(\eta_{ab}+2\pi\alpha' F_{ab})}.
$$

Use the expansion

$$
\det(1+M)=1+\operatorname{tr}M+
\frac12\left[(\operatorname{tr}M)^2-\operatorname{tr}(M^2)\right]+\cdots
$$

and the antisymmetry of $F_{ab}$ to explain why the leading gauge kinetic term is proportional to $F_{ab}F^{ab}$.

<details>
<summary><strong>Solution</strong></summary>

For an antisymmetric matrix $F_{ab}$,

$$
\operatorname{tr}F=0.
$$

Therefore the term linear in $F$ vanishes. The first nontrivial term is quadratic. Taking the square root of the determinant gives

$$
\sqrt{-\det(\eta+2\pi\alpha' F)}
=
1+
\frac{(2\pi\alpha')^2}{4}F_{ab}F^{ab}
+\cdots,
$$

up to signature conventions. The constant term is the brane tension, and the quadratic term gives the Maxwell kinetic term. For a stack of branes, the leading non-Abelian generalization gives the Yang–Mills kinetic term.

</details>

### Exercise 4: Why D3-branes are conformal candidates

Use the result

$$
[g_{{\rm YM},p+1}^2]=3-p
$$

to explain why D3-branes are special among flat D$p$-branes.

<details>
<summary><strong>Solution</strong></summary>

For D3-branes, $p=3$, so

$$
[g_{{\rm YM},4}^2]=0.
$$

The gauge coupling is dimensionless in four dimensions. A dimensionless coupling is compatible with conformal invariance, whereas a dimensionful coupling introduces a scale. The actual D3-brane low-energy theory is $\mathcal N=4$ SYM, whose beta function vanishes because of maximal supersymmetry. Thus D3-branes give a four-dimensional conformal field theory, making them the natural starting point for AdS$_5$/CFT$_4$.

</details>

### Exercise 5: Probe versus backreaction

Explain the difference between treating a D-brane as a probe and replacing a stack of D-branes by a supergravity solution.

<details>
<summary><strong>Solution</strong></summary>

A probe brane is studied in a fixed background while neglecting its own effect on the geometry. This is appropriate when the brane contributes a small amount of energy and charge compared with the background.

A backreacted brane is included as a source in the closed-string equations of motion. A large stack of $N$ branes can significantly curve spacetime. In the D3-brane derivation of AdS/CFT, the closed-string description is the backreacted geometry produced by the brane stack, not merely a probe in empty space.

</details>

### Exercise 6: The D3-brane radius and the 't Hooft coupling

For D3-branes, use

$$
L^4=4\pi g_sN\alpha'^2
$$

and the convention

$$
g_{\rm YM}^2=4\pi g_s
$$

to show that

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

<details>
<summary><strong>Solution</strong></summary>

The 't Hooft coupling is

$$
\lambda=g_{\rm YM}^2N.
$$

Using $g_{\rm YM}^2=4\pi g_s$, we get

$$
\lambda=4\pi g_sN.
$$

The D3-brane radius relation gives

$$
\frac{L^4}{\alpha'^2}=4\pi g_sN.
$$

Therefore

$$
\frac{L^4}{\alpha'^2}=\lambda.
$$

Thus large 't Hooft coupling means $L\gg\ell_s$, so the curvature radius is large compared with the string length. This is the condition that suppresses stringy $\alpha'$ corrections.

</details>

## Further reading

- J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).
- J. Polchinski, [Dirichlet-Branes and Ramond–Ramond Charges](https://arxiv.org/abs/hep-th/9510017).
- C. V. Johnson, [D-Brane Primer](https://arxiv.org/abs/hep-th/0007170).
- C. P. Bachas, [Lectures on D-branes](https://arxiv.org/abs/hep-th/9806199).
- J. M. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
