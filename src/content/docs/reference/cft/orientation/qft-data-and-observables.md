---
title: "QFT Data and Observables"
description: "The basic data of a local quantum field theory: Hilbert space, local operators, sources, generating functionals, correlation functions, Ward identities, and why these are the observables of holography."
sidebar:
  order: 2
---

## The point of this page

Before conformal symmetry enters, we need a clean answer to a basic question:

$$
\text{What is the actual data of a quantum field theory?}
$$

A first answer from ordinary QFT is: a Lagrangian. That answer is useful, but not invariant enough. Different Lagrangians can flow to the same infrared theory; gauge-fixed Lagrangians contain unphysical fields; and many CFTs, especially in strongly coupled regimes, are best understood without a weakly coupled Lagrangian at all.

A better answer is:

$$
\boxed{
\text{A local QFT is specified by its states, its local operators, and all correlation functions obeying locality, symmetry, and unitarity.}
}
$$

For a CFT, this answer sharpens dramatically. The full theory can be organized by the spectrum of local operators and their operator product expansion data. In a holographic CFT, this same data reorganizes into bulk fields, masses, couplings, and eventually geometry.

This page sets up the language that every later page will use:

$$
\begin{array}{ccl}
\text{operators} &\longleftrightarrow& \text{what the theory can measure},\\
\text{sources} &\longleftrightarrow& \text{how we perturb or probe the theory},\\
\text{generating functional} &\longleftrightarrow& \text{one object containing all correlators},\\
\text{Ward identities} &\longleftrightarrow& \text{symmetry constraints on observables},\\
\text{CFT data} &\longleftrightarrow& \text{the compact encoding of the fixed-point theory}.
\end{array}
$$

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Three viewpoints on QFT data and observables](/figures/cft/qft-data-observables.svg)

<figcaption>

Three equivalent ways to organize QFT data. The path-integral viewpoint emphasizes sources and $Z[J]$. The operator viewpoint emphasizes the Hilbert space, local operators, and Ward identities. In AdS/CFT, the same generating functional is reinterpreted as a bulk path integral with boundary values $\phi_\partial=J$, while CFT data such as $\Delta_i$, $\ell_i$, and $C_{ijk}$ becomes bulk spectral and interaction data.

</figcaption>
</figure>

## The local QFT machine

A local quantum field theory is a machine that assigns correlation functions to local observables. In a Euclidean path-integral presentation, the schematic definition is

$$
Z = \int [D\varphi] \; e^{-S_E[\varphi]},
$$

where $\varphi$ denotes the microscopic fields used in a particular description. These fields may or may not be gauge-invariant observables. In Yang--Mills theory, for example, $A_\mu^a$ is useful in the Lagrangian, but a gauge-invariant observable must be built from traces, Wilson loops, field strengths, or other gauge-invariant combinations.

A local operator is an object $\mathcal O(x)$ that can be inserted at a spacetime point. Typical examples are

$$
\phi(x),\qquad
\phi^2(x),\qquad
\bar\psi\psi(x),\qquad
F_{\mu\nu}F^{\mu\nu}(x),\qquad
J_\mu(x),\qquad
T_{\mu\nu}(x).
$$

The word “local” matters. It means that the operator probes a point, or more precisely a small neighborhood after renormalization. In an interacting QFT, composite operators such as $\phi^2(x)$ require renormalization. One should not imagine multiplying distributions at the same point naively. A properly defined local operator is a renormalized insertion.

The basic observables are correlation functions,

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

At separated points, these are the cleanest data of the theory. At coincident points, one meets contact terms, operator mixing, and scheme dependence. This distinction becomes important in CFT and essential in holographic renormalization.

> **AdS/CFT checkpoint.** In quantum gravity, local bulk fields are not gauge-invariant observables in a fundamental sense, because diffeomorphisms move points. Boundary CFT correlation functions are therefore not a decorative way to compute bulk physics; they are the precise gauge-invariant observables of the holographic theory.

## Two complementary definitions of the same theory

There are two standard languages for QFT.

The first is the Hilbert-space language. A Lorentzian QFT has a Hilbert space $\mathcal H$, a Hamiltonian $H$, symmetry generators, and operator-valued distributions $\mathcal O(t,\mathbf x)$ acting on states. Time-ordered correlation functions are vacuum expectation values,

$$
\langle 0|\,T\{\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\}\,|0\rangle.
$$

The second is the Euclidean path-integral language. After Wick rotation, many QFT observables can be packaged as Schwinger functions,

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle_E
=
\frac{1}{Z}\int [D\varphi]\,
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)e^{-S_E[\varphi]}.
$$

The two languages are not rivals. Under appropriate assumptions, Euclidean correlators satisfying reflection positivity reconstruct the Lorentzian Hilbert space and Wightman functions. For CFT, the Euclidean language is often cleaner for symmetry and OPE arguments, while the Lorentzian language is essential for causality, chaos, black holes, and real-time holography.

In this course we will move between these languages constantly. The dictionary is:

$$
\begin{array}{ccl}
\text{Euclidean path integral} &\longleftrightarrow& \text{Schwinger functions},\\
\text{Lorentzian Hilbert space} &\longleftrightarrow& \text{states and operator ordering},\\
\text{radial quantization} &\longleftrightarrow& \text{CFT-specific bridge between operators and states}.
\end{array}
$$

The next page will discuss Euclidean and Lorentzian signatures more carefully. For now, the important point is that the QFT data can be accessed through either sources in a path integral or operators acting on states.

## Sources: how to ask questions of a QFT

A source is a classical background field coupled to an operator. Given local operators $\mathcal O_A(x)$, define

$$
Z[J]
=
\left\langle
\exp\left(\sum_A\int d^d x\,J_A(x)\mathcal O_A(x)\right)
\right\rangle.
$$

Equivalently, in a Euclidean path integral,

$$
Z[J]
=
\int [D\varphi]\,
\exp\left(-S_E[\varphi]+\sum_A\int d^d x\,J_A(x)\mathcal O_A(x)\right).
$$

The sign convention is not sacred; what matters is consistency. With the convention above,

$$
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J_A(x)}
=
\langle \mathcal O_A(x)\rangle_J.
$$

At zero source,

$$
\left.
\frac{1}{Z[0]}
\frac{\delta^n Z[J]}
{\delta J_{A_1}(x_1)\cdots \delta J_{A_n}(x_n)}
\right|_{J=0}
=
\langle \mathcal O_{A_1}(x_1)\cdots \mathcal O_{A_n}(x_n)\rangle.
$$

It is often better to use the connected generating functional

$$
W[J]=\log Z[J].
$$

Then

$$
\left.
\frac{\delta^n W[J]}
{\delta J_{A_1}(x_1)\cdots \delta J_{A_n}(x_n)}
\right|_{J=0}
=
\langle \mathcal O_{A_1}(x_1)\cdots \mathcal O_{A_n}(x_n)\rangle_{\rm conn}.
$$

This is the first reason $Z[J]$ is central in AdS/CFT. The most compact form of the holographic dictionary is precisely an equality of generating functionals:

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}[\phi_\partial=J].
$$

The source $J_A(x)$ on the CFT side is the boundary value, or more precisely the leading asymptotic coefficient, of a bulk field $\phi_A$.

## Important sources and what they couple to

The most important sources are not optional decorations. They define universal operators.

| Source | Coupled operator | Meaning |
|---|---|---|
| Scalar source $J_A(x)$ | Scalar operator $\mathcal O_A(x)$ | Deforms or probes the theory by $\int J_A\mathcal O_A$ |
| Background metric $g_{\mu\nu}(x)$ | Stress tensor $T_{\mu\nu}(x)$ | Measures response to geometry |
| Background gauge field $A_\mu^a(x)$ | Conserved current $J_a^\mu(x)$ | Measures response to global symmetry sources |
| Fermionic source $\eta(x)$ | Fermionic operator $\Psi(x)$ | Needed for supersymmetric multiplets and spinor operators |

The stress tensor is defined as the response to the metric. In Euclidean signature, a common convention is

$$
\langle T_{\mu\nu}(x)\rangle_g
=
-\frac{2}{\sqrt g}\frac{\delta W[g]}{\delta g^{\mu\nu}(x)}.
$$

Some authors use the opposite sign depending on whether they vary $g_{\mu\nu}$ or $g^{\mu\nu}$ and depending on the convention for $W$. The important invariant statement is:

$$
T_{\mu\nu}\quad \text{is the operator sourced by the spacetime metric.}
$$

Similarly, a conserved current is sourced by a background gauge field:

$$
\delta S_E = -\int d^d x\sqrt g\, A_\mu^a J_a^\mu
$$

in one common Euclidean convention. The current expectation value is obtained by differentiating $W[A]$ with respect to $A_\mu^a$.

> **AdS/CFT checkpoint.** The universal CFT sources become universal bulk fields:
>
> $$
> \begin{array}{ccl}
> T_{\mu\nu} &\longleftrightarrow& \text{bulk metric } g_{MN},\\
> J_\mu^a &\longleftrightarrow& \text{bulk gauge field } A_M^a,\\
> \mathcal O_A &\longleftrightarrow& \text{bulk matter field } \phi_A.
> \end{array}
> $$
>
> This is not a mnemonic. It follows from the rule that sources are boundary values of bulk fields.

## Couplings are constant sources

A coupling is often a source frozen to a particular value. If a QFT action contains

$$
S_E = S_{E,0}+g\int d^d x\,\mathcal O(x),
$$

then the constant $g$ is the source for $\mathcal O$.

This point is small but powerful. The space of QFTs near a fixed point is coordinatized by sources for local operators:

$$
S_E = S_{\ast}+\sum_A g_A\int d^d x\,\mathcal O_A(x).
$$

The renormalization group describes how these couplings change with scale,

$$
\mu\frac{d g_A}{d\mu}=\beta_A(g).
$$

At a CFT fixed point, $\beta_A=0$ for the couplings that define the fixed point. Perturbing the CFT by $g_A\mathcal O_A$ asks whether the deformation grows, shrinks, or remains marginal in the infrared.

If $\mathcal O$ has scaling dimension $\Delta$, then dimensional analysis gives

$$
[g]=d-\Delta.
$$

Thus:

$$
\begin{array}{rcll}
\Delta<d &\Longrightarrow& g \text{ has positive mass dimension} & \text{relevant},\\
\Delta=d &\Longrightarrow& g \text{ is dimensionless} & \text{marginal},\\
\Delta>d &\Longrightarrow& g \text{ has negative mass dimension} & \text{irrelevant}.
\end{array}
$$

This classification will reappear in the radial direction of AdS. Relevant deformations correspond to boundary conditions that strongly affect the infrared geometry; irrelevant deformations are subtle because they are nonrenormalizable from the boundary viewpoint and often correspond to changing UV boundary data.

## Local operators are not always elementary fields

In a free scalar theory, it is tempting to identify the basic local operator with the elementary field $\phi(x)$. But this is a special situation. In an interacting theory, and especially in a gauge theory, the local operator basis is much larger and more physical than the elementary Lagrangian fields.

For example, in four-dimensional Yang--Mills theory, gauge-invariant local operators include

$$
\operatorname{Tr}F_{\mu\nu}F^{\mu\nu},
\qquad
\operatorname{Tr}F_{\mu\nu}\widetilde F^{\mu\nu},
\qquad
\operatorname{Tr}\left(\Phi^{I_1}\cdots \Phi^{I_k}\right),
\qquad
\operatorname{Tr}\left(\bar\psi\Gamma D_{\mu_1}\cdots D_{\mu_n}\psi\right),
$$

with appropriate subtractions and mixing. In $\mathcal N=4$ SYM, single-trace scalar operators such as

$$
\operatorname{Tr}\left(\Phi^{(I_1}\cdots \Phi^{I_k)}\right)-\text{traces}
$$

are central because they map to Kaluza--Klein modes on $S^5$ in the canonical $AdS_5\times S^5$ duality.

The lesson is:

$$
\text{the operator basis, not the elementary field list, is the invariant language of QFT.}
$$

This is especially true for CFT, where local operators organize into representations of the conformal group.

## Correlators as response functions

The source formalism makes correlation functions look like response coefficients. Expanding $W[J]$ around $J=0$ gives

$$
\begin{aligned}
W[J]
=\, &W[0]
+\sum_A\int d^d x\,J_A(x)\langle\mathcal O_A(x)\rangle\\
&+\frac{1}{2}\sum_{A,B}\int d^d x\,d^d y\,J_A(x)J_B(y)
\langle\mathcal O_A(x)\mathcal O_B(y)\rangle_{\rm conn}
+\cdots .
\end{aligned}
$$

Thus the one-point function is the first response to a source, the connected two-point function is the linear response of one operator to another source, and higher connected correlators are nonlinear response coefficients.

This viewpoint is very useful in holography. Near the AdS boundary, a scalar field behaves schematically as

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)+z^\Delta A(x),
\qquad z\to 0.
$$

The coefficient $J(x)$ is the source. The coefficient $A(x)$ is related, after renormalization, to the response $\langle\mathcal O(x)\rangle_J$.

So the elementary holographic pair is not “field and field.” It is

$$
\boxed{
\text{source } J
\quad \longleftrightarrow \quad
\text{response } \langle\mathcal O\rangle_J.
}
$$

The bulk field is the device that computes the response.

## Symmetries and Ward identities

Symmetries constrain correlation functions. In a local QFT, a continuous global symmetry gives a conserved current,

$$
\partial_\mu J^\mu_a=0,
$$

up to contact terms and possible anomalies. The associated charge is

$$
Q_a=\int_{\Sigma} d\Sigma_\mu\,J_a^\mu,
$$

and it acts on local operators by commutators in Lorentzian signature:

$$
[Q_a,\mathcal O_i(x)] = - (t_a)_i{}^j\mathcal O_j(x),
$$

with conventions depending on whether $t_a$ is chosen Hermitian or anti-Hermitian.

Inside correlation functions, current conservation becomes a Ward identity. Schematically,

$$
\partial_\mu\langle J_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle\mathcal O_1(x_1)\cdots (t_a\mathcal O_k)(x_k)\cdots\mathcal O_n(x_n)\rangle.
$$

The delta functions are not a nuisance. They say that the current is conserved except where it meets charged operator insertions.

The stress tensor gives analogous Ward identities for spacetime symmetries. Translation invariance gives

$$
\partial_\mu\langle T^{\mu\nu}(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-\sum_{k=1}^n\delta^{(d)}(x-x_k)\partial_{x_k}^\nu
\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

for scalar operators, again up to convention-dependent signs and contact terms.

In a CFT, the trace Ward identity becomes central. In flat space and away from anomalies, conformal invariance implies

$$
T^\mu{}_{\mu}=0.
$$

More generally, along an RG flow one expects the schematic relation

$$
T^\mu{}_{\mu}
=
\sum_A \beta_A\mathcal O_A + \text{anomalies} + \text{improvement/contact terms}.
$$

This formula is a bridge between RG and conformal symmetry. It is also the field-theoretic ancestor of holographic RG equations.

> **AdS/CFT checkpoint.** Ward identities become bulk constraints. Current conservation is tied to bulk gauge invariance. Stress-tensor conservation is tied to bulk diffeomorphism invariance. The CFT does not merely have the same symmetries as the bulk; it encodes the constraints that make the bulk theory gauge-invariant.

## Operator products and short-distance data

Correlation functions become singular when points approach each other. The operator product expansion organizes this singularity. In a general local QFT, one writes schematically

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\sum_C f_{AB}{}^C(x;\mu,g)\,\mathcal O_C(0),
\qquad x\to 0.
$$

In a CFT, scale invariance makes the structure much sharper. For scalar primary operators,

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\sum_C C_{AB}{}^C\,|x|^{\Delta_C-\Delta_A-\Delta_B}\mathcal O_C(0)+\text{descendants}.
$$

The numbers $C_{AB}{}^C$ are OPE coefficients. They are not optional data; they are the multiplication table of local operators.

For CFT, the operator spectrum and OPE coefficients determine all correlation functions, at least in the standard bootstrap viewpoint. That is why the natural CFT data are

$$
\boxed{
\mathcal D_{\rm CFT}
=
\{\Delta_i,\ell_i,R_i,C_{ijk}\}.
}
$$

Here $\Delta_i$ is the scaling dimension, $\ell_i$ is spin, $R_i$ denotes global-symmetry representation data, and $C_{ijk}$ are three-point/OPE coefficients.

This is the point where CFT becomes much more rigid than generic QFT. A generic QFT has scale-dependent couplings and correlation functions with running. A CFT packages its local dynamics into scale-invariant operator algebra data.

## Connected, disconnected, and large-$N$ correlators

The distinction between connected and disconnected correlators is crucial for holography. Suppose a theory has a large-$N$ expansion such that the connected correlators of suitably normalized single-trace operators scale as

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\rm conn}
\sim
N^{2-n}.
$$

Then, for two single-trace operators,

$$
\langle \mathcal O_1\mathcal O_2\rangle_{\rm conn}\sim N^0,
$$

while a four-point function has a disconnected part of order $N^0$ and a connected part of order $N^{-2}$:

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle
=
\langle \mathcal O\mathcal O\rangle\langle \mathcal O\mathcal O\rangle
+\text{permutations}
+\frac{1}{N^2}\,G_{\rm conn}+\cdots .
$$

This is large-$N$ factorization. It is the CFT reason why the bulk theory becomes weakly coupled. Disconnected correlators describe free multi-particle propagation; connected correlators describe interactions.

The small parameter of bulk perturbation theory is therefore not mysterious. It is the inverse measure of the number of CFT degrees of freedom.

## What counts as “the same QFT”?

A QFT can be described in many redundant ways. Field redefinitions, gauge fixing, dualities, and different UV completions may lead to the same IR observables. Therefore, when we say “the QFT,” we usually mean an equivalence class of descriptions that produce the same physical correlation functions.

Several layers of data should be distinguished:

$$
\begin{array}{ccl}
\text{microscopic presentation} &:& \text{fields, action, regulator, bare couplings},\\
\text{renormalized QFT} &:& \text{renormalized operators and correlators at scale }\mu,\\
\text{CFT fixed point} &:& \text{scale-invariant operator spectrum and OPE data},\\
\text{holographic CFT} &:& \text{CFT data with large-}N\text{ structure and sparse spectrum}.
\end{array}
$$

This hierarchy prevents a common confusion: a Lagrangian is not the same as the theory. It is a useful presentation of the theory. The observables are correlation functions of gauge-invariant operators, line operators, defect operators, and other invariant probes.

In AdS/CFT, this distinction becomes existential. The same bulk theory may be invisible from a naive list of elementary boundary fields; it is visible in the organization of boundary operator data.

## Contact terms and scheme dependence

A mature use of correlation functions requires knowing what is universal. At separated points, CFT two- and three-point functions are highly constrained and their coefficients are physical once operator normalizations are fixed. At coincident points, correlation functions can have contact terms such as

$$
\delta^{(d)}(x-y),
\qquad
\partial_\mu\delta^{(d)}(x-y),
\qquad
\Box\delta^{(d)}(x-y).
$$

These can often be shifted by adding local counterterms to the generating functional. For example, a source counterterm

$$
\int d^d x\sqrt g\,J(x)\Box J(x)
$$

changes the two-point function of $\mathcal O$ by a contact term. It does not change separated-point physics.

This is why one must be careful when saying that $Z[J]$ contains all observables. It does, but some pieces are scheme-dependent. Holographic renormalization is precisely the bulk procedure that separates finite physical data from local counterterm ambiguities.

## Euclidean data, Lorentzian physics

Euclidean correlators are often the most efficient way to define a QFT nonperturbatively. But Lorentzian physics requires operator ordering. A Euclidean two-point function analytically continued to Lorentzian signature can produce different real-time correlators depending on the continuation prescription:

$$
\langle T\{\mathcal O(x)\mathcal O(0)\}\rangle,
\qquad
\langle \mathcal O(x)\mathcal O(0)\rangle,
\qquad
\langle [\mathcal O(x),\mathcal O(0)]\rangle,
\qquad
G_R(x)=i\theta(t)\langle[\mathcal O(x),\mathcal O(0)]\rangle.
$$

The retarded correlator $G_R$ governs causal response. Thermal Wightman functions govern emission and absorption. Out-of-time-order correlators diagnose chaos. These distinctions are not visible if one only stares at a Euclidean expression without specifying analytic continuation.

For AdS/CFT this is a major issue. Euclidean bulk saddle points compute Euclidean partition functions and thermal free energies. Lorentzian bulk boundary conditions compute retarded correlators, quasinormal modes, causal propagation, and black-hole response.

The next page will make this Euclidean/Lorentzian distinction explicit.

## The minimal data needed for AdS/CFT

For the purpose of learning holography, the following QFT data should become second nature.

First, know the operator spectrum:

$$
\mathcal O_i,
\qquad
\Delta_i,
\qquad
\ell_i,
\qquad
R_i.
$$

Second, know how operators are sourced:

$$
\delta S = \sum_i \int d^d x\,J_i\mathcal O_i.
$$

Third, know how to extract correlators:

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle
=
\left.
\frac{1}{Z[0]}\frac{\delta^n Z[J]}{\delta J_1\cdots\delta J_n}
\right|_{J=0}.
$$

Fourth, know the universal operators:

$$
T_{\mu\nu},
\qquad
J_\mu^a,
\qquad
\text{relevant and marginal scalar operators},
\qquad
\text{protected operators in supersymmetric theories}.
$$

Fifth, know the operator algebra:

$$
\mathcal O_i\times\mathcal O_j
\sim
\sum_k C_{ij}{}^k\mathcal O_k.
$$

Sixth, know which limits produce semiclassical bulk physics:

$$
\text{large }N,
\qquad
\text{large gap in higher-spin single-trace operators},
\qquad
\text{strong coupling when needed},
\qquad
\text{sparse low-dimension spectrum}.
$$

These are the ingredients that make the holographic dictionary meaningful rather than ceremonial.

## Common pitfalls

### Pitfall 1: confusing microscopic fields with observables

The field $\varphi$ in a path integral is often not a gauge-invariant observable. The physical objects are operators and their correlation functions. In gauge theory, this distinction is non-negotiable.

### Pitfall 2: treating $Z[J]$ as only a formal object

$Z[J]$ is formal if left unrenormalized, but after renormalization it is the most compact way to define the response of the theory to all local probes. In holography, $Z[J]$ is the object equated to the bulk path integral.

### Pitfall 3: ignoring contact terms

Ward identities often include contact terms. These are not errors. They encode how currents and stress tensors act on operator insertions.

### Pitfall 4: forgetting operator mixing

Operators with the same quantum numbers can mix under renormalization. At a CFT, one usually chooses a basis of scaling operators that diagonalizes the dilatation operator. Away from a fixed point, this basis runs with scale.

### Pitfall 5: assuming every CFT has a simple gravity dual

Every holographic gravity dual defines a CFT, but not every CFT has a weakly curved Einstein-like dual. Large $N$ and a sparse spectrum are additional dynamical conditions.

## Summary

The fundamental language of QFT is not “fields in a Lagrangian,” but rather

$$
\boxed{
\text{states} + \text{operators} + \text{correlation functions} + \text{symmetry constraints}.
}
$$

Sources package observables into a generating functional,

$$
Z[J]=\left\langle e^{\int J\mathcal O}\right\rangle,
$$

and differentiating $Z[J]$ or $W[J]=\log Z[J]$ gives full or connected correlators. The stress tensor and conserved currents are universal because they are sourced by background geometry and background gauge fields. Ward identities express the action of symmetries on correlation functions.

For CFT, the same QFT data condenses into operator dimensions, spins, symmetry representations, and OPE coefficients:

$$
\{\Delta_i,\ell_i,R_i,C_{ijk}\}.
$$

For AdS/CFT, this data becomes the bulk spectrum, interactions, and gauge constraints. So the road to holography begins by taking QFT observables seriously.

## Exercises

### Exercise 1: full versus connected correlators

Let

$$
Z[J]=\left\langle e^{\int d^d x\,J(x)\mathcal O(x)}\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Assume $Z[0]=1$. Show that

$$
\left.\frac{\delta^2 W}{\delta J(x)\delta J(y)}\right|_{J=0}
=
\langle\mathcal O(x)\mathcal O(y)\rangle
-
\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle.
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
\frac{\delta W}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}.
$$

Differentiate once more:

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}
=
\frac{1}{Z}\frac{\delta^2 Z}{\delta J(x)\delta J(y)}
-
\frac{1}{Z^2}\frac{\delta Z}{\delta J(x)}\frac{\delta Z}{\delta J(y)}.
$$

At $J=0$ and $Z[0]=1$,

$$
\left.\frac{\delta Z}{\delta J(x)}\right|_{J=0}
=
\langle\mathcal O(x)\rangle,
$$

and

$$
\left.\frac{\delta^2 Z}{\delta J(x)\delta J(y)}\right|_{J=0}
=
\langle\mathcal O(x)\mathcal O(y)\rangle.
$$

Therefore

$$
\left.\frac{\delta^2 W}{\delta J(x)\delta J(y)}\right|_{J=0}
=
\langle\mathcal O(x)\mathcal O(y)\rangle
-
\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle.
$$

This is the connected two-point function.

</details>

### Exercise 2: dimension of a source

In a $d$-dimensional CFT, a scalar operator $\mathcal O$ has scaling dimension $\Delta$. Its source appears through

$$
\delta S=\int d^d x\,J(x)\mathcal O(x).
$$

Find the scaling dimension of $J$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. In mass units, the measure has dimension

$$
[d^d x]=-d,
$$

while

$$
[\mathcal O]=\Delta.
$$

Therefore

$$
[J]+\Delta-d=0.
$$

So

$$
[J]=d-\Delta.
$$

Equivalently, if $\Delta<d$, the source has positive mass dimension and the deformation is relevant. If $\Delta=d$, it is marginal. If $\Delta>d$, it is irrelevant.

</details>

### Exercise 3: Ward identity from current conservation

Let $J^\mu$ be the conserved current for a $U(1)$ symmetry. Suppose local operators $\mathcal O_k$ have charges $q_k$, so that

$$
[Q,\mathcal O_k]=q_k\mathcal O_k.
$$

Show that the current Ward identity has the schematic form

$$
\partial_\mu\langle J^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
\sum_{k=1}^n q_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

up to sign conventions.

<details><summary><strong>Solution</strong></summary>

Consider integrating the divergence over a small ball $B_k$ surrounding $x_k$ and no other insertion:

$$
\int_{B_k} d^d x\,\partial_\mu J^\mu
=
\int_{\partial B_k} d\Sigma_\mu J^\mu.
$$

The surface integral computes the charge acting on the operator at $x_k$. Therefore, inside a correlator,

$$
\int_{B_k} d^d x\,\partial_\mu
\langle J^\mu(x)\mathcal O_1\cdots\mathcal O_n\rangle
=
q_k\langle\mathcal O_1\cdots\mathcal O_n\rangle,
$$

with a sign depending on whether one defines $[Q,\mathcal O]=q\mathcal O$ or $\delta\mathcal O=i\alpha[Q,\mathcal O]$ and on Euclidean continuation conventions.

A distribution whose integral over a small ball around $x_k$ gives $q_k$ times the correlator is

$$
q_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\mathcal O_n\rangle.
$$

Summing over all insertions gives the Ward identity.

</details>

### Exercise 4: stress tensor as metric response

Let $W[g]$ be the Euclidean connected generating functional. Suppose

$$
\delta W[g]
=
-\frac{1}{2}\int d^d x\sqrt g\,\langle T_{\mu\nu}\rangle\delta g^{\mu\nu}.
$$

Show that an infinitesimal Weyl transformation $\delta g^{\mu\nu}=-2\sigma g^{\mu\nu}$ gives

$$
\delta_\sigma W[g]
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Insert the Weyl variation into the definition:

$$
\delta_\sigma W[g]
=
-\frac{1}{2}\int d^d x\sqrt g\,\langle T_{\mu\nu}\rangle(-2\sigma g^{\mu\nu}).
$$

The factors $-1/2$ and $-2$ multiply to $+1$, so

$$
\delta_\sigma W[g]
=
\int d^d x\sqrt g\,\sigma g^{\mu\nu}\langle T_{\mu\nu}\rangle.
$$

Since

$$
T^\mu{}_{\mu}=g^{\mu\nu}T_{\mu\nu},
$$

we obtain

$$
\delta_\sigma W[g]
=
\int d^d x\sqrt g\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

Thus Weyl invariance of $W[g]$ implies $\langle T^\mu{}_{\mu}\rangle=0$, up to anomalies and contact terms.

</details>

### Exercise 5: why large-$N$ factorization suggests weak bulk coupling

Assume single-trace operators are normalized so that

$$
\langle \mathcal O\mathcal O\rangle_{\rm conn}\sim N^0,
\qquad
\langle \mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim \frac{1}{N},
\qquad
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim \frac{1}{N^2}.
$$

Explain why this resembles a weakly coupled bulk theory.

<details><summary><strong>Solution</strong></summary>

In an ordinary weakly coupled field theory, normalize a field so that its two-point function is order one. If the cubic interaction has coupling $g$, then a connected three-point function is order $g$, and a connected tree-level four-point interaction or exchange contribution is order $g^2$.

The large-$N$ CFT pattern is

$$
\langle \mathcal O\mathcal O\rangle\sim 1,
\qquad
\langle \mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim \frac{1}{N},
\qquad
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim \frac{1}{N^2}.
$$

This matches a bulk perturbation theory with effective coupling

$$
g_{\rm bulk}\sim \frac{1}{N}.
$$

Disconnected CFT correlators represent free propagation of multiple bulk particles. Connected correlators represent interactions. Thus large-$N$ factorization is the boundary reason that the bulk theory can become semiclassical and weakly interacting.

</details>
