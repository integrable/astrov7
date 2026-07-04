---
title: "Statement of the Correspondence"
description: "The precise meaning of AdS/CFT as an equivalence between a boundary quantum field theory and bulk quantum gravity, including sources, operators, states, partition functions, and controlled limits."
sidebar:
  order: 10
---

The previous unit explained how the canonical AdS$_5$/CFT$_4$ example arises from D3-branes and why the large-$N$, large-$\lambda$ regime admits a classical supergravity approximation. We now begin the dictionary itself.

The first point is conceptual but absolutely essential: AdS/CFT is not merely a recipe for approximating a strongly coupled quantum field theory by a convenient gravitational model. In its sharp examples, it is a proposed equivalence between two descriptions of the same quantum system.

For the canonical example, the full statement is

$$
\mathcal N=4\;SU(N)\;\text{super-Yang–Mills on the boundary}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

The commonly used classical gravity formula is a limit of this statement, not the statement itself. The hierarchy is

$$
Z_{\mathrm{CFT}}
=
Z_{\mathrm{string}}
\longrightarrow
Z_{\mathrm{sugra}}
\approx
\exp\!\left(-S_{\text{ren,on-shell}}\right),
$$

where the first equality is the duality, the arrow to supergravity uses a low-energy/large-gap limit such as large $\lambda$, and the final saddle-point approximation uses large $N$.

This page explains what is being equated, what data must be specified, and what the slogan

$$
\text{bulk gravity}
\quad\longleftrightarrow\quad
\text{boundary quantum field theory}
$$

really means.

<figure class="doc-figure" style="--figure-width: 60rem;">

![The logical layers of the AdS/CFT correspondence: exact quantum equality, controlled expansion, classical saddle, and dictionary entries.](/figures/course/statement-of-correspondence.svg)

<figcaption>

The logical layers of AdS/CFT. The exact statement equates a boundary CFT generating functional with a bulk string-theory partition function subject to asymptotically AdS boundary conditions. Large $N$ and a large stringy gap produce a weakly quantum local bulk effective theory. The familiar on-shell action formula is the leading classical saddle approximation.

</figcaption>
</figure>

## Why this matters

Many early mistakes in learning AdS/CFT come from using the right formula with the wrong interpretation.

For example, it is common to say that a boundary source is “equal to” the boundary value of a bulk field. That is a good first sentence, but it hides several choices: the conformal frame of the boundary metric, the normalization of the operator, the boundary condition imposed on the bulk field, possible counterterms, and sometimes the quantization scheme. Similarly, saying that a black hole is “dual to” a thermal state is correct only after one specifies the ensemble, the boundary manifold, the dominant saddle, and the time contour.

The dictionary is powerful because it is precise. But its precision comes from saying what object on one side is equal to what object on the other side.

The cleanest object is the partition functional with sources.

## The exact statement in generating-functional form

Let $M_d$ be the $d$-dimensional spacetime on which the CFT lives. Let $g_{(0)ij}$ be a representative of its conformal metric class, and let $J_i(x)$ denote sources for local operators $\mathcal O_i(x)$. The CFT generating functional is

$$
Z_{\mathrm{CFT}}[g_{(0)},J_i]
=
\left\langle
\exp\!\left(
\sum_i \int_{M_d} d^d x\,\sqrt{|g_{(0)}|}\,J_i(x)\mathcal O_i(x)
\right)
\right\rangle_{g_{(0)}}.
$$

The bulk side is a string-theory partition function over asymptotically AdS configurations whose boundary data are fixed by the same sources:

$$
Z_{\mathrm{string}}[g_{(0)},J_i]
=
\int_{\substack{\mathrm{asymptotically\;AdS}\\
\Phi_i^{(0)}=J_i,\;G\to g_{(0)}}}
\mathcal D G\,\mathcal D\Phi_i\,\mathcal D(\text{strings, branes})\;
\exp(-S_{\mathrm{string}}).
$$

The correspondence says

$$
Z_{\mathrm{CFT}}[g_{(0)},J_i]
=
Z_{\mathrm{string}}[g_{(0)},J_i].
$$

This is the most compact functional statement of the duality. It should be read with several important qualifications.

First, the bulk is not just a fixed spacetime. In the full theory, the metric and other fields are dynamical, and one should sum over all configurations compatible with the prescribed asymptotic data.

Second, the boundary metric is a source. It couples to the stress tensor $T^{ij}$, so varying $g_{(0)ij}$ gives stress-tensor correlators.

Third, the equality is an equality of regulated and renormalized objects. Infinite AdS volume produces divergences, and those divergences match ultraviolet divergences in the CFT. The precise equality uses holographic renormalization.

Fourth, the word “source” is not just bookkeeping. Changing a source changes the boundary theory by adding an external field or coupling. On the bulk side this is implemented by changing the asymptotic boundary condition.

## The canonical example

For AdS$_5$/CFT$_4$, the boundary theory is four-dimensional $\mathcal N=4$ SYM. The bulk theory is type IIB string theory on asymptotically $\mathrm{AdS}_5\times S^5$ backgrounds with $N$ units of self-dual five-form flux through the $S^5$.

The schematic statement is

$$
Z_{\mathcal N=4\,\mathrm{SYM}}
\left[
  g_{(0)},
  A_{(0)},
  \phi_{(0)}^I,
  \ldots;
  N,\tau_{\mathrm{YM}}
\right]
=
Z_{\mathrm{IIB}}
\left[
  G\to g_{(0)},
  A\to A_{(0)},
  \Phi^I\to \phi_{(0)}^I,
  \ldots;
  N,\tau_{\mathrm{IIB}}
\right].
$$

Here $A_{(0)}$ denotes possible background gauge fields for global symmetries, $\phi_{(0)}^I$ denotes sources for scalar operators, and the dots denote the rest of the supergravity/string modes. The complex coupling is matched to the IIB axio-dilaton:

$$
\tau_{\mathrm{YM}}
=
\frac{\theta_{\mathrm{YM}}}{2\pi}
+
\frac{4\pi i}{g_{\mathrm{YM}}^2},
\qquad
\tau_{\mathrm{IIB}}
=
C_0+
\frac{i}{g_s}.
$$

With the convention used in this course,

$$
g_{\mathrm{YM}}^2=4\pi g_s,
\qquad
\theta_{\mathrm{YM}}=2\pi C_0,
\qquad
\frac{L^4}{\alpha'^2}=\lambda=g_{\mathrm{YM}}^2N.
$$

This example is special because both sides are known very explicitly. The boundary theory is a well-defined quantum field theory, and the bulk theory is a standard string theory background in a controlled flux sector.

## Equality of partition functions means equality of correlators

The equality of generating functionals implies equality of all correlation functions obtained by functional differentiation.

With the source convention used in the course,

$$
W[J]=\log Z[J],
\qquad
\delta W[J]
=
\sum_i\int d^d x\,\sqrt{|g_{(0)}|}\,
\langle \mathcal O_i(x)\rangle_J\,\delta J_i(x).
$$

Thus

$$
\langle \mathcal O_i(x)\rangle_J
=
\frac{1}{\sqrt{|g_{(0)}|}}
\frac{\delta W[J]}{\delta J_i(x)}.
$$

The two-point function is obtained by differentiating again:

$$
\langle \mathcal O_i(x)\mathcal O_j(y)\rangle_{c,J}
=
\frac{1}{\sqrt{|g_{(0)}(x)|}\sqrt{|g_{(0)}(y)|}}
\frac{\delta^2 W[J]}{\delta J_i(x)\delta J_j(y)}.
$$

The GKP/Witten prescription, developed on the next pages, says that at leading classical order

$$
W_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J]
$$

in Euclidean signature. Consequently,

$$
\langle \mathcal O_{i_1}(x_1)\cdots\mathcal O_{i_n}(x_n)\rangle_c
=
-\frac{\delta^n S_{\text{ren,on-shell}}[J]}
{\delta J_{i_1}(x_1)\cdots\delta J_{i_n}(x_n)}\bigg|_{J=0},
$$

up to the conventional factors of $\sqrt{|g_{(0)}|}$ and possible signs depending on the source convention. The minus sign here comes from $W\approx -S_{\text{ren,on-shell}}$ in Euclidean signature.

:::note
In Lorentzian signature, the saddle is written with $e^{iS}$ rather than $e^{-S_E}$, and real-time correlators require a choice of time contour and boundary conditions. The Euclidean formula is the cleanest first statement, but it is not the whole real-time dictionary.
:::

## The source-boundary-value map

For a scalar field $\Phi$ in asymptotically $\mathrm{AdS}_{d+1}$, the near-boundary expansion takes the schematic form

$$
\Phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x)
+
\cdots,
\qquad
z\to0.
$$

The leading coefficient $\phi_{(0)}(x)$ is interpreted as the source for a boundary operator $\mathcal O(x)$ of scaling dimension $\Delta$:

$$
\int d^d x\,\phi_{(0)}(x)\mathcal O(x).
$$

The subleading response coefficient $A(x)$ is related to the expectation value $\langle \mathcal O(x)\rangle$, after holographic renormalization.

The mass of the scalar and the scaling dimension of the operator are related by

$$
m^2L^2=\Delta(\Delta-d).
$$

This relation is one of the cleanest examples of the dictionary: a bulk geometric parameter becomes boundary conformal data.

The same logic applies to other fields:

| Bulk field | Boundary source | Boundary operator |
|---|---|---|
| scalar $\Phi$ | scalar coupling $\phi_{(0)}$ | scalar operator $\mathcal O$ |
| gauge field $A_M$ | background gauge field $A_{(0)i}$ | conserved current $J^i$ |
| metric $G_{MN}$ | boundary metric $g_{(0)ij}$ | stress tensor $T^{ij}$ |
| gravitino | background gravitino source | supercurrent |
| spinor $\Psi$ | fermionic source | fermionic operator |

The metric entry is especially important. The CFT stress tensor is defined by the response to the boundary metric:

$$
\delta W
=
\frac{1}{2}
\int d^d x\,\sqrt{|g_{(0)}|}\,
\langle T^{ij}\rangle\,\delta g_{(0)ij}.
$$

On the bulk side, $g_{(0)ij}$ is the leading term in the asymptotic metric. Thus the boundary stress tensor is extracted from the renormalized gravitational action by varying the boundary metric.

## Equality of Hilbert spaces and spectra

The generating-functional statement is not the only way to say the correspondence. On global AdS, the boundary is the cylinder

$$
\mathbb R_t\times S^{d-1}.
$$

The CFT quantized on this cylinder has a Hilbert space $\mathcal H_{\mathrm{CFT}}$. The bulk theory on global AdS has a Hilbert space $\mathcal H_{\mathrm{bulk}}$, with states such as gravitons, strings, branes, and black holes.

AdS/CFT says that these are two descriptions of the same Hilbert space:

$$
\mathcal H_{\mathrm{CFT}}
\cong
\mathcal H_{\mathrm{bulk}}.
$$

This is not a trivial statement. The two descriptions organize states very differently.

In the CFT, states can be created by local operators through radial quantization. A primary operator $\mathcal O$ of dimension $\Delta$ creates a state on the sphere with energy

$$
E_{\mathrm{cyl}}=\Delta.
$$

In the bulk, the corresponding single-particle excitation is a normal mode in global AdS. Descendant states correspond to acting with derivatives or momenta, which raise the global energy by integers. Multi-trace operators correspond, at leading large $N$, to multiparticle bulk states.

This is why the state-operator correspondence is not a side topic. It is the CFT version of the bulk spectrum.

## Equality of symmetries

A basic consistency check is the symmetry match.

For Lorentzian $\mathrm{AdS}_{d+1}$,

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})=SO(2,d),
$$

which is the global conformal group of a $d$-dimensional Lorentzian CFT. In the canonical example,

$$
\mathrm{Isom}(S^5)=SO(6)\simeq SU(4),
$$

which is the R-symmetry group of $\mathcal N=4$ SYM. Supersymmetry extends this match to the full superconformal symmetry.

The symmetry match does not prove the correspondence, but it is one of the reasons the dictionary is rigid. Bulk fields must transform in representations that match boundary operators.

For example, a bulk gauge symmetry associated with an isometry of the internal space corresponds to a global symmetry of the boundary theory. This is not a contradiction: gauge redundancies in the bulk become global symmetries at the boundary because gauge transformations that approach nonzero boundary values act as physical transformations of the boundary sources.

## Equality of states and ensembles

The partition function also depends on the state or ensemble.

Some basic examples are:

| Boundary description | Bulk description |
|---|---|
| CFT vacuum on $\mathbb R\times S^{d-1}$ | global AdS |
| local operator insertion | bulk excitation sourced from the boundary |
| single-trace primary | single-particle bulk state |
| multi-trace operator | multiparticle bulk state |
| thermal state on the sphere | thermal AdS or AdS black hole, depending on temperature and saddle |
| thermal state on $\mathbb R^{d-1}$ | planar AdS black brane |
| finite chemical potential | asymptotic value of a bulk gauge field |

The distinction between sources and states is important. A source changes the Hamiltonian or action. A state chooses which vector or density matrix in the Hilbert space is being used. Bulk boundary conditions encode sources; normalizable data encode states or expectation values.

For example, turning on a scalar source changes the CFT Lagrangian by adding

$$
\int \phi_{(0)}\mathcal O.
$$

By contrast, an excited state with $\langle \mathcal O\rangle\neq0$ can have no source. In the bulk, that distinction appears as the difference between the non-normalizable and normalizable parts of a field.

## Classical gravity as a controlled limit

The exact partition function is generally too hard to compute. The practical power of AdS/CFT comes from controlled limits.

In the canonical example,

$$
\frac{G_5}{L^3}\sim\frac{1}{N^2},
\qquad
\frac{\alpha'}{L^2}=\frac{1}{\sqrt\lambda}.
$$

The large-$N$ limit suppresses bulk quantum loops. The large-$\lambda$ limit suppresses stringy curvature corrections. In this regime the string partition function can be approximated by a supergravity path integral:

$$
Z_{\mathrm{string}}[J]
\longrightarrow
Z_{\mathrm{sugra}}[J]
=
\int_{\Phi_i^{(0)}=J_i}\mathcal D G\,\mathcal D\Phi_i\,
\exp(-S_{\mathrm{sugra}}[G,\Phi_i]).
$$

If the supergravity action is large in AdS units, this path integral is dominated by classical saddles:

$$
Z_{\mathrm{sugra}}[J]
\approx
\sum_{\text{saddles }a}
\exp\!\left(-S_{\mathrm{ren}}[G_a,\Phi_{i,a};J]\right).
$$

When a single saddle dominates,

$$
W_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

When several saddles compete, the dominant one gives the leading large-$N$ answer, and a change of dominance becomes a large-$N$ phase transition. The Hawking–Page transition is the standard example.

## What is local, and what is not

AdS/CFT does not identify a local bulk point with a local boundary point. A bulk field $\Phi(z,x)$ depends on the radial coordinate $z$, but the boundary theory has no extra spatial coordinate called $z$.

The radial direction is encoded nonlocally in the boundary theory. Roughly,

$$
\text{radial position in AdS}
\quad\leftrightarrow\quad
\text{energy scale in the CFT},
$$

but this is not an ordinary coordinate transformation. It is a statement about how scale transformations act:

$$
x^i\to \Lambda x^i,
\qquad
z\to \Lambda z.
$$

Local bulk effective field theory emerges only in a special large-$N$ and large-gap regime. At finite $N$, or without a large gap to stringy/higher-spin states, the boundary theory may still be perfectly well defined, but the bulk description need not resemble classical local gravity.

## Boundary conditions are part of the theory

A bulk field equation does not define a unique dual problem until boundary conditions are specified.

For a scalar field, the two independent near-boundary falloffs are

$$
\Phi(z,x)
\sim
z^{\Delta_-}\alpha(x)+z^{\Delta_+}\beta(x),
\qquad
\Delta_\pm=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

In standard quantization, the slower falloff is treated as the source, and the faster falloff is related to the expectation value. In a certain mass window, alternate quantization is possible, and the roles are changed. Mixed boundary conditions correspond to multi-trace deformations of the CFT.

So the statement

$$
\Phi_{(0)}=J
$$

is shorthand. The precise dictionary specifies which coefficient is held fixed, what counterterms are used, and which variational principle is well posed.

## The role of holographic renormalization

The equality of partition functions is not literally an equality of finite unregulated integrals.

In Poincaré coordinates,

$$
ds^2=\frac{L^2}{z^2}(dz^2+g_{ij}dx^i dx^j),
$$

the boundary lies at $z=0$. The on-shell gravitational action typically diverges as the cutoff surface $z=\epsilon$ approaches the boundary. The renormalized action is defined schematically by

$$
S_{\mathrm{ren}}
=
\lim_{\epsilon\to0}
\left(
S_{\mathrm{bulk}}^{z\ge\epsilon}
+S_{\mathrm{GHY}}^{z=\epsilon}
+S_{\mathrm{ct}}^{z=\epsilon}
\right).
$$

The counterterms are local functionals of the induced fields at the cutoff surface. They are the bulk representation of UV renormalization in the boundary theory.

This is why the next several pages will distinguish carefully between raw asymptotic coefficients and renormalized one-point functions.

## What the correspondence does not say

It is just as important to know what is not being claimed.

AdS/CFT does not say that every QFT has a simple weakly curved gravity dual. Most QFTs do not. A CFT with a classical Einstein-like bulk dual needs very special large-$N$ properties and a sparse spectrum of low-dimension single-trace operators.

AdS/CFT does not say that the boundary theory lives “on the surface of a black hole.” The boundary is the conformal boundary of AdS, not a material screen at finite distance.

AdS/CFT does not say that classical gravity is exact. Classical gravity is the leading saddle in a limit. Stringy and quantum corrections are real, and they correspond to finite-coupling and finite-$N$ effects in the CFT.

AdS/CFT does not give, by itself, a complete theory of de Sitter quantum gravity or flat-space quantum gravity. There are related holographic ideas in other asymptotics, but the AdS dictionary is especially sharp because AdS has a timelike conformal boundary on which an ordinary quantum theory can live.

AdS/CFT also does not make bulk locality fundamental. Bulk locality is emergent and approximate. The boundary theory is the nonperturbative definition in the best-understood examples.

## Dictionary checkpoint

The core statement of the correspondence is

$$
Z_{\mathrm{CFT}}[g_{(0)},J_i]
=
Z_{\mathrm{string}}[g_{(0)},J_i].
$$

The basic source-operator map is

$$
J_i(x)
\quad\leftrightarrow\quad
\text{asymptotic boundary data for a bulk field }\Phi_i,
$$

and

$$
\mathcal O_i(x)
\quad\leftrightarrow\quad
\text{the bulk field }\Phi_i.
$$

In Euclidean classical gravity,

$$
W_{\mathrm{CFT}}[J]
=
\log Z_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

The first functional derivative gives one-point functions; higher derivatives give connected correlators.

The classical gravity recipe is reliable only in a controlled limit, typically large $N$ and large gap or large $\lambda$.

## Common confusions

### “The bulk theory and the boundary theory are two different systems that interact.”

No. In AdS/CFT they are two descriptions of the same system. One does not put a CFT next to an AdS spacetime and let them exchange energy. The equality says that the CFT Hilbert space and the bulk quantum-gravity Hilbert space are two ways of organizing the same quantum states.

### “The boundary source is the whole bulk field.”

No. The source is the boundary datum of the bulk field. The bulk field in the interior is determined by solving the bulk equations with that boundary condition and with a choice of state or interior regularity condition.

### “The on-shell action is the CFT action.”

No. The on-shell action is a functional of sources that computes the CFT generating functional in a saddle approximation. It is not the microscopic CFT Lagrangian.

### “A black hole means the boundary theory is gravitational.”

No. The boundary theory remains an ordinary non-gravitational quantum theory. The black hole is the bulk representation of a high-energy or thermal state of that theory.

### “The dictionary is unique without choices.”

Not quite. Boundary conditions, counterterm schemes, operator normalizations, quantization choices, and ensembles must be specified. Physical quantities are scheme-independent when they should be, but intermediate formulas often are not.

## Exercises

### Exercise 1: Source dimension

Let $\mathcal O$ be a scalar primary operator of scaling dimension $\Delta$ in a $d$-dimensional CFT. If the deformation

$$
\int d^d x\,J(x)\mathcal O(x)
$$

is dimensionless, what is the scaling dimension of the source $J$?

<details>
<summary><strong>Solution</strong></summary>

The measure has dimension

$$
[d^d x]=-d,
$$

and the operator has dimension $\Delta$. For the integral to be dimensionless,

$$
[J]+\Delta-d=0.
$$

Thus

$$
[J]=d-\Delta.
$$

This matches the AdS near-boundary behavior

$$
\Phi(z,x)\sim z^{d-\Delta}\phi_{(0)}(x),
$$

where the power $d-\Delta$ is the scaling weight of the source.

</details>

### Exercise 2: Stress tensor as a response

Suppose the CFT generating functional depends on a background metric $g_{(0)ij}$ and satisfies

$$
\delta W
=
\frac12\int d^d x\,\sqrt{|g_{(0)}|}\,\langle T^{ij}\rangle\delta g_{(0)ij}.
$$

Write $\langle T^{ij}\rangle$ as a functional derivative of $W$.

<details>
<summary><strong>Solution</strong></summary>

By comparing coefficients of $\delta g_{(0)ij}$, we get

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{|g_{(0)}(x)|}}
\frac{\delta W}{\delta g_{(0)ij}(x)}.
$$

In the classical Euclidean gravity limit,

$$
W\approx -S_{\text{ren,on-shell}},
$$

so

$$
\langle T^{ij}(x)\rangle
\approx
-\frac{2}{\sqrt{|g_{(0)}(x)|}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta g_{(0)ij}(x)}.
$$

Different sign conventions for the Euclidean source coupling can shift this sign, so the important invariant statement is that the boundary stress tensor is obtained by varying the renormalized on-shell gravitational action with respect to the boundary metric.

</details>

### Exercise 3: Why large $N$ gives a saddle

Assume a bulk effective action has the schematic form

$$
S_{\mathrm{bulk}}=\frac{L^{d-1}}{G_N}\,\widehat S.
$$

If $L^{d-1}/G_N\sim N^2$, explain why the bulk path integral is dominated by classical saddles at large $N$.

<details>
<summary><strong>Solution</strong></summary>

The Euclidean bulk path integral is schematically

$$
Z_{\mathrm{bulk}}
=\int \mathcal D\Phi\,\exp\!\left(-\frac{L^{d-1}}{G_N}\widehat S[\Phi]\right).
$$

If

$$
\frac{L^{d-1}}{G_N}\sim N^2,
$$

then the exponential contains a large parameter. In the large-$N$ limit, configurations away from stationary points are strongly suppressed by destructive/steepest-descent behavior. The leading answer is therefore determined by classical solutions satisfying

$$
\frac{\delta \widehat S}{\delta \Phi}=0.
$$

Fluctuations around the saddle produce loop corrections suppressed by powers of $G_N/L^{d-1}\sim 1/N^2$.

</details>

### Exercise 4: Why weakly coupled SYM is not classical gravity

In AdS$_5$/CFT$_4$, use

$$
\frac{L^4}{\alpha'^2}=\lambda
$$

to explain why weakly coupled $\mathcal N=4$ SYM does not have a weakly curved classical supergravity description.

<details>
<summary><strong>Solution</strong></summary>

The curvature radius in string units is

$$
\frac{L}{\ell_s}=\lambda^{1/4},
\qquad
\ell_s=\sqrt{\alpha'}.
$$

If $\lambda\ll1$, then

$$
L\ll \ell_s.
$$

The would-be AdS radius is smaller than the string length, so the bulk is highly stringy. The classical supergravity approximation assumes curvature radii much larger than the string scale, namely $L\gg\ell_s$, which requires $\lambda\gg1$. Thus weakly coupled SYM may be tractable by perturbative field theory, but its dual bulk description is not weakly curved classical gravity.

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
