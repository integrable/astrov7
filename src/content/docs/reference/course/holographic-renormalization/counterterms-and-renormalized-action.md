---
title: "Counterterms and the Renormalized Action"
description: "How local boundary counterterms remove AdS infrared divergences and define the finite holographic generating functional."
sidebar:
  order: 30
---

The previous page developed the near-boundary expansion. We now use it to construct the object that actually enters the holographic dictionary: the renormalized on-shell action.

The raw bulk action evaluated on a solution is almost never finite. The divergence is not a bug in the correspondence. It is the gravitational image of ultraviolet divergences in the boundary QFT. Holographic renormalization removes these divergences by adding local boundary counterterms at a radial cutoff surface and then taking the cutoff away.

The basic definition is

$$
S_{\rm ren}[\text{sources}]
=
\lim_{\epsilon\to0}
\left(
S_{\rm reg}^{z\ge \epsilon}
+
S_{{\rm ct},\epsilon}
\right).
$$

Here $S_{\rm reg}$ is the bulk action, including any boundary terms needed for a well-posed variational problem, evaluated on the region $z\ge \epsilon$. The counterterm action $S_{{\rm ct},\epsilon}$ is a local covariant functional of fields induced on the cutoff surface $z=\epsilon$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A radial cutoff regulates AdS. The regulated on-shell action has local divergences. Boundary counterterms cancel them, leaving a finite renormalized action depending on the sources and the renormalization scale.](/figures/course/counterterms-renormalized-action.svg)

<figcaption>

The counterterm construction. Cut off the asymptotically AdS region at $z=\epsilon$, evaluate the regulated on-shell action, expand its divergences using the near-boundary solution, add local covariant counterterms on $\Sigma_\epsilon$, and remove the cutoff. Logarithmic terms leave dependence on a renormalization scale $\mu$ and encode anomalies.

</figcaption>
</figure>

## Why this matters

The formula

$$
Z_{\rm CFT}[J]
\approx
\exp\left(-S_{\text{on-shell}}[J]\right)
$$

is false if $S_{\text{on-shell}}$ means the unrenormalized bulk action. The correct semiclassical statement is

$$
Z_{\rm CFT}[J]
\approx
\exp\left(-S_{\text{ren,on-shell}}[J]\right)
$$

in Euclidean signature with the conventions used in this course.

Counterterms are therefore not optional decorations. They are required to define finite correlation functions, finite one-point functions, finite stress tensors, and finite thermodynamic potentials. Without them, even pure AdS has an infinite volume and a divergent gravitational action.

There are three conceptual lessons:

1. **Divergences are local.** Near-boundary divergences are determined by local source data.
2. **Renormalized answers are finite but scheme-dependent.** Finite local counterterms can change contact terms and local pieces of one-point functions.
3. **Nonlocal physics survives.** The normalizable data selected by the interior condition are not removed by counterterms; they encode the state and long-distance response.

## The radial cutoff

Use Fefferman–Graham coordinates near the conformal boundary:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{ij}(z,x)dx^i dx^j\right),
\qquad
z\to0.
$$

Regulate the spacetime by cutting it off at

$$
\Sigma_\epsilon:\quad z=\epsilon.
$$

The induced metric on the cutoff surface is

$$
\gamma_{ij}(\epsilon,x)
=
\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x),
$$

and the finite boundary metric source is the conformal representative

$$
g_{(0)ij}(x)=\lim_{z\to0}g_{ij}(z,x).
$$

For a bulk field $\Phi$, the cutoff value $\Phi(\epsilon,x)$ is not itself the finite source. For a scalar in standard quantization,

$$
\phi(z,x)
=
z^{d-\Delta}\phi_{(0)}(x)+\cdots,
$$

so the source is extracted by rescaling:

$$
\phi_{(0)}(x)
=
\lim_{\epsilon\to0}\epsilon^{\Delta-d}\phi(\epsilon,x).
$$

This is why counterterms are naturally written on $\Sigma_\epsilon$ using $\gamma_{ij}$ and the cutoff fields. They are covariant from the cutoff-surface viewpoint, but after expansion in $\epsilon$ they become ordinary UV counterterms for the boundary sources.

## Regulated action versus renormalized action

The regulated on-shell action has an asymptotic expansion of the form

$$
S_{\rm reg}(\epsilon)
=
\sum_{n>0}\epsilon^{-n}S_{(n)}[\text{sources}]
+
\log(\epsilon\mu)S_{\log}[\text{sources}]
+
S_{\rm finite}[\text{sources},\text{state}]
+
O(\epsilon).
$$

The coefficients $S_{(n)}$ and $S_{\log}$ are local functionals of the sources. The finite piece can contain nonlocal dependence, because it knows about the solution in the interior.

The counterterm action is chosen to cancel the divergent local pieces:

$$
S_{{\rm ct},\epsilon}
=
-
\sum_{n>0}\epsilon^{-n}S_{(n)}[\text{sources}]
-
\log(\epsilon\mu)S_{\log}[\text{sources}]
+
S_{\rm finite,local}[\text{sources}].
$$

The optional finite local term $S_{\rm finite,local}$ is a choice of renormalization scheme. The renormalized action is then

$$
S_{\rm ren}
=
S_{\rm finite}+S_{\rm finite,local}.
$$

This is exactly analogous to ordinary QFT renormalization: divergent local terms are subtracted, while finite local terms remain scheme choices.

## Why the counterterms are local

The near-boundary expansion is recursive. For a scalar field,

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}+z^2\phi_{(2)}+z^4\phi_{(4)}+\cdots
\right)
+
z^\Delta
\left(A+\cdots\right),
$$

where the coefficients $\phi_{(2)},\phi_{(4)},\ldots$ are local functions of $\phi_{(0)}$ until one reaches the normalizable order. The coefficient $A$ is state-dependent and is determined only after imposing an interior condition.

Divergences arise from the early, locally determined part of the expansion. Therefore they can be cancelled by local counterterms. The nonlocal information carried by $A$ contributes to finite terms and cannot be cancelled by local counterterms.

The same idea applies to the metric. The Fefferman–Graham expansion is schematically

$$
g_{ij}(z,x)
=
g_{(0)ij}
+z^2g_{(2)ij}
+\cdots
+z^d g_{(d)ij}
+z^d\log z^2\,h_{(d)ij}
+\cdots.
$$

The early coefficients are local curvature functionals of $g_{(0)ij}$, while $g_{(d)ij}$ contains the state-dependent stress tensor data subject to Ward identities. Thus the gravitational counterterms are built from local curvature invariants of the cutoff metric $\gamma_{ij}$.

## Scalar example: leading counterterm

Take a scalar field in Euclidean AdS$_{d+1}$ with action

$$
S_\phi
=
\frac{\mathcal N_\phi}{2}
\int d^{d+1}x\sqrt{g}
\left(
 g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2
\right).
$$

On shell, the bulk action reduces to a boundary term:

$$
S_{\phi,\text{reg,on-shell}}
=
\frac{\mathcal N_\phi}{2}
\int_{\Sigma_\epsilon}d^d x\sqrt{\gamma}\,
\phi\, n^M\partial_M\phi,
$$

where $n^M$ is the outward unit normal to the regulated region. For the region $z\ge\epsilon$, this normal points toward decreasing $z$.

In standard quantization,

$$
\phi(z,x)
=
z^{\Delta_-}\phi_{(0)}(x)+\cdots,
\qquad
\Delta_-=d-\Delta.
$$

The leading divergence is cancelled by

$$
S_{\phi,{\rm ct}}^{(0)}
=
\mathcal N_\phi
\int_{\Sigma_\epsilon} d^d x\sqrt{\gamma}\,
\frac{d-\Delta}{2L}\phi^2.
$$

The factor $1/L$ appears because $\phi^2$ is integrated with the cutoff metric $\gamma_{ij}$ and the normal derivative has dimension $1/L$.

The next counterterm, when it is not replaced by a logarithmic term, is

$$
S_{\phi,{\rm ct}}^{(2)}
=
\mathcal N_\phi
\int_{\Sigma_\epsilon} d^d x\sqrt{\gamma}\,
\frac{L}{2(2\Delta-d-2)}
\phi\Box_\gamma\phi.
$$

Here $\Box_\gamma$ is the Laplacian built from the cutoff metric. This expression is valid away from the resonance

$$
2\Delta-d-2=0.
$$

At the resonance, the corresponding divergence is logarithmic and the counterterm contains $\log(\epsilon\mu)$.

A useful way to read the formula is:

$$
\text{radial divergence}
\quad\longleftrightarrow\quad
\text{local boundary operator made from sources}.
$$

The scalar counterterm series continues with higher derivatives. It usually has the schematic form

$$
S_{\phi,{\rm ct}}
=
\mathcal N_\phi
\int_{\Sigma_\epsilon} d^d x\sqrt{\gamma}
\left[
\frac{d-\Delta}{2L}\phi^2
+
\frac{L}{2(2\Delta-d-2)}\phi\Box_\gamma\phi
+
\cdots
\right].
$$

In curved boundary backgrounds, additional terms involving the cutoff curvature also appear, such as $R[\gamma]\phi^2$.

## Gravitational counterterms

For pure Einstein gravity with negative cosmological constant, a convenient Euclidean convention is

$$
S_{\rm grav,reg}
=
-
\frac{1}{2\kappa_{d+1}^2}
\int_{M_\epsilon}d^{d+1}x\sqrt{g}
\left(
R+\frac{d(d-1)}{L^2}
\right)
-
\frac{1}{\kappa_{d+1}^2}
\int_{\Sigma_\epsilon}d^d x\sqrt{\gamma}\,K.
$$

The second term is the Gibbons–Hawking–York term. It is required for a Dirichlet variational problem for the metric: the induced metric is held fixed at the cutoff surface.

For this convention, the first gravitational counterterms are

$$
S_{{\rm grav},\rm ct}
=
\frac{1}{\kappa_{d+1}^2}
\int_{\Sigma_\epsilon}d^d x\sqrt{\gamma}
\left[
\frac{d-1}{L}
+
\frac{L}{2(d-2)}R[\gamma]
+
\cdots
\right].
$$

For $d>4$, the next curvature-squared counterterm can be written as

$$
S_{{\rm grav},\rm ct}^{(4)}
=
\frac{1}{\kappa_{d+1}^2}
\int_{\Sigma_\epsilon}d^d x\sqrt{\gamma}\,
\frac{L^3}{2(d-4)(d-2)^2}
\left(
R_{ij}[\gamma]R^{ij}[\gamma]
-
\frac{d}{4(d-1)}R[\gamma]^2
\right).
$$

The poles at $d=2$ and $d=4$ are not pathologies. They signal logarithmic counterterms and conformal anomalies in even-dimensional boundary CFTs.

For example, in a four-dimensional boundary CFT, the curvature-squared structure associated with the logarithmic term is responsible for the Weyl anomaly. This is the gravitational version of the statement that logarithmic UV divergences leave a renormalization-scale dependence.

## Pure AdS as the simplest check

Consider Euclidean Poincaré AdS$_{d+1}$:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+d\vec x^{\,2}\right).
$$

The volume element is

$$
\sqrt g
=
\frac{L^{d+1}}{z^{d+1}}.
$$

The regulated volume diverges as

$$
\int_\epsilon dz\,\frac{L^{d+1}}{z^{d+1}}
=
\frac{L^{d+1}}{d\epsilon^d}+\cdots.
$$

The leading gravitational counterterm is proportional to the cutoff volume

$$
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma
=
\int d^d x\frac{L^d}{\epsilon^d}.
$$

Thus the leading divergence of the bulk volume can be cancelled by a local boundary cosmological constant term on the cutoff surface. This elementary example captures the whole logic: an infinite radial volume becomes a local UV divergence in the boundary theory.

## Counterterms and the variational problem

Counterterms do two jobs at once:

$$
\text{finite action}
\quad\text{and}\quad
\text{finite variation}.
$$

The second point is just as important as the first. Holographic one-point functions are obtained by varying $S_{\rm ren}$ with respect to sources. If the variation of the regulated action diverges, the one-point function is not well defined.

At the cutoff surface, the on-shell variation has the schematic form

$$
\delta S_{\text{reg,on-shell}}
=
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma
\left(
\Pi_\phi\delta\phi
+
\Pi_A^i\delta A_i
+\frac12\Pi_g^{ij}\delta\gamma_{ij}
+\cdots
\right),
$$

where the $\Pi$'s are radial canonical momenta. The counterterms contribute additional local terms to these momenta:

$$
\Pi_{\rm ren}
=
\Pi_{\rm reg}+\Pi_{\rm ct}.
$$

The finite limit of $\Pi_{\rm ren}$ is the practical object that gives one-point functions. This is why the next page focuses on variation: once the renormalized action is constructed, its variation is the dictionary.

## Renormalization scale and anomalies

When logarithmic divergences appear, the counterterm action contains terms such as

$$
S_{\rm ct}^{\log}
=
-
\log(\epsilon\mu)
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma\,\mathcal A[\gamma,\phi,A,\ldots].
$$

The scale $\mu$ is arbitrary. Changing $\mu$ shifts the renormalized action by a finite local functional:

$$
\mu\frac{d}{d\mu}S_{\rm ren}
=
-
\int d^d x\sqrt{g_{(0)}}\,\mathcal A[g_{(0)},\phi_{(0)},A_{(0)},\ldots].
$$

In the boundary theory, this is the conformal anomaly or, more generally, a local term in the Callan–Symanzik equation. The anomaly is not removable by choosing a clever scheme. Its detailed representative can shift by finite counterterms, but its cohomologically nontrivial content is physical.

## Finite counterterms and scheme dependence

After divergences have been cancelled, one may still add finite local counterterms, for example

$$
S_{\rm finite,local}
=
\int d^d x\sqrt{g_{(0)}}
\left(
 c_1 R[g_{(0)}]^2
 +c_2 \phi_{(0)}\Box_{g_{(0)}}\phi_{(0)}
 +c_3 F_{(0)ij}F_{(0)}^{ij}
 +\cdots
\right).
$$

These terms change contact terms in correlation functions and local terms in one-point functions. They do not change nonlocal separated-point singularity structure or pole locations of retarded correlators. In thermodynamics they can shift scheme-dependent vacuum energies but should not change physical differences once a scheme is fixed.

A good rule is:

$$
\text{finite local ambiguity}
=
\text{renormalization scheme, not new bulk dynamics}.
$$

This is especially important when comparing formulas across papers. Two authors may both be correct while using different finite counterterms.

## Dirichlet, Neumann, and mixed boundary conditions

The counterterm action above is naturally adapted to Dirichlet boundary conditions: the source is held fixed. For a scalar in standard quantization, this means fixing $\phi_{(0)}$.

Other choices are possible in special mass ranges or for gauge fields and gravitons in lower dimensions. Neumann or mixed boundary conditions are implemented by adding finite boundary terms or Legendre transforms. In the CFT, these choices correspond to changing which operator is sourced or to adding multi-trace deformations.

Thus the phrase “the counterterms” always means counterterms plus a choice of variational problem. The divergent terms are fixed by finiteness. The finite boundary terms encode scheme and boundary-condition choices.

## Practical recipe

For a classical holographic computation, the counterterm workflow is:

1. **Choose a cutoff.** Work on $z\ge\epsilon$ or another asymptotic radial cutoff.
2. **Fix the variational problem.** Include the Gibbons–Hawking–York term for gravity and any required boundary terms for matter.
3. **Solve near the boundary.** Expand the fields in powers and possible logarithms of $z$.
4. **Evaluate the regulated action.** Keep all divergent terms as $\epsilon\to0$.
5. **Write local counterterms.** Express the divergent terms covariantly using the cutoff fields and $\gamma_{ij}$.
6. **Take the limit.** Define $S_{\rm ren}$ by adding counterterms and sending $\epsilon\to0$.
7. **Fix finite scheme choices.** State any finite local counterterms or subtraction conventions.
8. **Vary $S_{\rm ren}$.** Obtain one-point functions and then higher correlators.

The most common mistake is to skip step 8 and identify a coefficient in the expansion directly with a vev. Coefficients are useful, but the dictionary is variational.

## Dictionary checkpoint

The counterterm dictionary is:

| Bulk object | Boundary interpretation |
|---|---|
| radial cutoff $z=\epsilon$ | UV regulator of the QFT |
| local divergent terms in $S_{\rm reg}$ | UV divergences determined by sources |
| $S_{\rm ct}$ | local QFT counterterms |
| logarithmic counterterms | conformal anomalies and RG scale dependence |
| finite local counterterms | renormalization scheme choices |
| $S_{\text{ren,on-shell}}$ | semiclassical generating functional, up to the sign convention $W\approx -S_{\rm ren}$ |

The clean formula is therefore

$$
W_{\rm CFT}[\text{sources}]
\approx
-S_{\text{ren,on-shell}}[\text{sources}]
$$

in the Euclidean convention used here.

## Common confusions

### “Counterterms live on the actual boundary.”

Operationally they are written on the cutoff surface $\Sigma_\epsilon$. Only after they are added does one take $\epsilon\to0$. Their finite limit is interpreted as ordinary local counterterms in the boundary QFT.

### “Counterterms are arbitrary.”

The divergent counterterms are fixed by the requirement of finiteness and locality. Finite local counterterms are scheme choices. Confusing these two statements causes endless trouble.

### “A counterterm can remove any unwanted term.”

Only local source-dependent terms can be removed. A nonlocal dependence on sources, a pole in a retarded Green's function, or a state-dependent normalizable response is not removable by a local counterterm.

### “The Gibbons–Hawking–York term is a counterterm.”

No. The Gibbons–Hawking–York term is part of the regulated gravitational action needed for a Dirichlet variational principle. It does not by itself cancel all AdS divergences. The holographic counterterms are added in addition to it.

### “The renormalized action is unique.”

It is unique only after choosing a scheme and boundary conditions. Physical claims should either be scheme-independent or state the scheme explicitly.

## Exercises

### Exercise 1: Pure AdS volume divergence

In Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+d\vec x^{\,2}\right),
$$

show that the regulated volume divergence is proportional to $\epsilon^{-d}$.

<details>
<summary><strong>Solution</strong></summary>

The determinant is

$$
\sqrt g=\frac{L^{d+1}}{z^{d+1}}.
$$

Therefore, per unit boundary coordinate volume,

$$
\int_\epsilon^\infty dz\sqrt g
=
L^{d+1}\int_\epsilon^\infty \frac{dz}{z^{d+1}}
=
\frac{L^{d+1}}{d\epsilon^d}.
$$

The divergence is local because it is proportional to the boundary volume. Indeed,

$$
\sqrt\gamma=\frac{L^d}{\epsilon^d},
$$

so the leading gravitational counterterm is proportional to $\int_{\Sigma_\epsilon}\sqrt\gamma$.

</details>

### Exercise 2: Leading scalar counterterm

Assume

$$
\phi(z,x)=z^{\Delta_-}\phi_{(0)}(x)+\cdots,
\qquad
\Delta_-=d-\Delta.
$$

Using $n^z=-z/L$ near the cutoff surface, show that the leading scalar on-shell action has a divergence proportional to $-\Delta_-\epsilon^{2\Delta_- - d}\phi_{(0)}^2/2$ per unit normalization, and explain why the counterterm proportional to $\Delta_-\phi^2/(2L)$ cancels it.

<details>
<summary><strong>Solution</strong></summary>

Near $z=\epsilon$,

$$
\partial_z\phi=\Delta_- z^{\Delta_- -1}\phi_{(0)}+\cdots,
\qquad
n^z\partial_z\phi=-\frac{z}{L}\partial_z\phi
=-\frac{\Delta_-}{L}z^{\Delta_-}\phi_{(0)}+\cdots.
$$

Also

$$
\sqrt\gamma=\frac{L^d}{\epsilon^d}+\cdots.
$$

Thus the leading on-shell boundary term is

$$
\frac12\int\sqrt\gamma\,\phi n^M\partial_M\phi
=
-
\frac12 L^{d-1}\Delta_-\epsilon^{2\Delta_- - d}\phi_{(0)}^2+\cdots.
$$

The counterterm

$$
\int\sqrt\gamma\,\frac{\Delta_-}{2L}\phi^2
$$

contributes

$$
+
\frac12L^{d-1}\Delta_-\epsilon^{2\Delta_- - d}\phi_{(0)}^2+
\cdots,
$$

which cancels the divergence.

</details>

### Exercise 3: Why local counterterms cannot remove normalizable data

Explain why a local counterterm built from $\phi(\epsilon,x)$ and $\gamma_{ij}(\epsilon,x)$ cannot remove an arbitrary nonlocal dependence of $A(x)$ on $\phi_{(0)}(x)$.

<details>
<summary><strong>Solution</strong></summary>

The coefficient $A(x)$ is determined by solving the bulk equation with an interior condition. In momentum space, for example, regularity in Euclidean AdS typically makes $A(k)$ a non-polynomial function of $k$ times $\phi_{(0)}(k)$. A local counterterm corresponds to a finite number, or an asymptotic series, of local derivatives of the source. In momentum space it produces polynomial terms in $k^2$.

Therefore local counterterms can alter contact terms and local derivative terms, but they cannot cancel the genuinely nonlocal part of $A[\phi_{(0)}]$. That nonlocal part is the physical correlator.

</details>

### Exercise 4: Logarithmic counterterms and scale dependence

Suppose a regulated action contains

$$
S_{\rm reg}\supset \log\epsilon\int d^d x\sqrt{g_{(0)}}\,\mathcal A(x).
$$

Why must the counterterm introduce a scale $\mu$, and what does the resulting $\mu$ dependence mean in the CFT?

<details>
<summary><strong>Solution</strong></summary>

The logarithm requires a dimensionless argument. A counterterm that cancels the divergence is written using

$$
\log(\epsilon\mu),
$$

where $\mu$ is an arbitrary renormalization scale. After the divergence is cancelled, changing $\mu$ shifts the finite renormalized action by

$$
\mu\frac{dS_{\rm ren}}{d\mu}
=
-
\int d^d x\sqrt{g_{(0)}}\,\mathcal A(x)
$$

up to the sign convention for the subtraction. In the CFT this is the local anomaly or RG scale dependence of the generating functional. In a conformal theory on a curved background, it is the Weyl anomaly.

</details>

## Further reading

- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- I. Papadimitriou and K. Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
