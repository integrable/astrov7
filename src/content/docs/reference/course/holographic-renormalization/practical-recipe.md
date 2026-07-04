---
title: "Practical Recipe"
description: "A step-by-step workflow for holographic renormalization: choose sources, solve near the boundary, add counterterms, vary the renormalized action, and check Ward identities."
sidebar:
  order: 70
---

The previous pages built the machinery of holographic renormalization piece by piece: near-boundary expansions, counterterms, renormalized one-point functions, Ward identities, anomalies, and the radial Hamilton–Jacobi interpretation. This page compresses that machinery into a practical workflow.

The goal is simple. Given an asymptotically AdS bulk problem, you want to extract finite CFT data:

$$
\text{sources}
\quad\longrightarrow\quad
S_{\rm ren}
\quad\longrightarrow\quad
\langle \mathcal O\rangle,
\;\langle J^i\rangle,
\;\langle T^{ij}\rangle,
\;\text{correlators}.
$$

The danger is also simple. It is easy to read off the wrong coefficient, forget a counterterm, confuse a state with a source, or impose a boundary condition that computes the wrong Green's function. Holographic renormalization is the safety system that prevents those errors.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A workflow diagram for holographic renormalization. The steps are: specify action and sources; choose Fefferman-Graham gauge and cutoff; solve the asymptotic expansion; evaluate the regulated action and variation; add counterterms; take the finite limit; vary the renormalized action; check Ward identities. Interior conditions fix the response, and finite local terms choose a scheme or ensemble.](/figures/course/holographic-renormalization-practical-recipe.svg)

<figcaption>

The practical workflow. Near-boundary analysis determines the divergent local terms. Interior regularity, ingoing boundary conditions, or a chosen state determines the response. Counterterms remove the cutoff dependence. Finite local terms choose a scheme or ensemble. The final test is whether the renormalized one-point functions obey the correct Ward identities.

</figcaption>
</figure>

## Why this matters

The formal definition

$$
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left(
S_{\rm bulk}^{z\ge \epsilon}
+
S_{\rm GHY}^{z=\epsilon}
+
S_{\rm ct}^{z=\epsilon}
\right)
$$

is compact, but a calculation never starts from this equation alone. A real computation has choices:

- Which boundary data are fixed?
- Which radial coordinate and cutoff are being used?
- Which subleading coefficients are determined locally by the source, and which are genuine response data?
- Which counterterms are required by covariance and locality?
- Which finite terms are scheme choices?
- Which interior condition selects the state or Green's function?

This page is written as a checklist for those decisions. It is not meant to replace the derivations; it is meant to make them usable.

## The one-line algorithm

For an asymptotically AdS problem, do this:

$$
\boxed{
\begin{array}{c}
\text{fix sources}
\to
\text{solve near the boundary}
\to
\text{regularize}
\to
\text{add local counterterms}
\\
\to
\text{take }\epsilon\to0
\to
\text{vary }S_{\rm ren}
\to
\text{check Ward identities}.
\end{array}}
$$

Everything else is refinement.

A more explicit version is:

| Step | Task | Output |
|---|---|---|
| 1 | Specify bulk action and variational problem | sources, boundary conditions, ensemble |
| 2 | Choose an asymptotic coordinate system | cutoff surface $\Sigma_\epsilon$ and induced fields |
| 3 | Solve the near-boundary expansion | source data, local terms, response data, possible logs |
| 4 | Impose the interior condition | state, saddle, or Green's function |
| 5 | Evaluate $S_{\rm reg}$ and $\delta S_{\rm reg}$ | divergent cutoff action and raw momenta |
| 6 | Add $S_{\rm ct}$ | finite variational problem |
| 7 | Remove the cutoff | $S_{\rm ren}$ and renormalized momenta |
| 8 | Differentiate | one-point functions and correlators |
| 9 | Check identities | conservation, trace, gauge Ward identities, anomalies |

The order matters. In particular, do not impose a numerical horizon condition and then read off a vev before you have fixed the source convention and counterterms.

## Step 1: specify the action and the variational problem

Start with the bulk action, including all boundary terms needed for the chosen variational problem. For gravity, Dirichlet boundary conditions on the induced metric require the Gibbons–Hawking–York term. For gauge fields, scalars, or mixed boundary conditions, additional finite boundary terms may be needed.

A typical two-derivative bulk action has the form

$$
S_{\rm bulk}
=
\int_M d^{d+1}x\sqrt{g}\,
\mathcal L(g,\phi,A,\ldots).
$$

For Einstein gravity with negative cosmological constant,

$$
S_{\rm grav}
=
-\frac{1}{16\pi G_{d+1}}
\int_M d^{d+1}x\sqrt{g}\,
\left(R+\frac{d(d-1)}{L^2}\right)
-
\frac{1}{8\pi G_{d+1}}
\int_{\partial M} d^d x\sqrt{\gamma}\,K
+
S_{\rm ct},
$$

in a common Euclidean convention. Different sign conventions are common. The invariant instruction is not the sign in this displayed equation; it is this:

$$
\boxed{
\text{the total action must have a finite and well-defined variation for the sources being held fixed.}}
$$

Before solving anything, decide what the boundary theory is being asked to compute.

### Typical source choices

For standard Dirichlet holography:

| Bulk field | Boundary source | Boundary operator |
|---|---|---|
| scalar $\phi$ | $\phi_{(0)}$ | scalar operator $\mathcal O$ |
| gauge field $A_i$ | $A_{(0)i}$ | current $J^i$ |
| metric $g_{ij}$ | boundary metric $g_{(0)ij}$ | stress tensor $T^{ij}$ |

The source convention used in this course is Euclidean

$$
Z_{\rm CFT}[J]
=
\left\langle
\exp\!\left(
\int d^d x\sqrt{g_{(0)}}\,J\mathcal O
\right)
\right\rangle,
\qquad
W_{\rm CFT}=\log Z_{\rm CFT}.
$$

In the classical gravity limit,

$$
W_{\rm CFT}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

Therefore, with this convention,

$$
\langle\mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta W_{\rm CFT}}{\delta J(x)}
\approx
-
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta J(x)}.
$$

If your bulk-action or source convention differs by a sign, the final sign changes. The algorithm does not change, but the sign bookkeeping must be consistent from the first line.

## Step 2: choose an asymptotic coordinate system

The cleanest coordinate system for holographic renormalization is Fefferman–Graham gauge:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{ij}(z,x)dx^i dx^j
\right),
\qquad
z\to0.
$$

The cutoff surface is

$$
\Sigma_\epsilon:\quad z=\epsilon.
$$

The induced metric on $\Sigma_\epsilon$ is

$$
\gamma_{ij}(\epsilon,x)
=
\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x).
$$

The boundary metric source is the conformal representative

$$
g_{(0)ij}(x)
=
\lim_{z\to0} g_{ij}(z,x).
$$

Do not confuse $\gamma_{ij}$ and $g_{(0)ij}$. The first is the induced metric at a finite cutoff and diverges like $\epsilon^{-2}$. The second is the finite CFT metric source.

### When Fefferman–Graham gauge is not convenient

Fefferman–Graham gauge is excellent near the boundary, but it is often inconvenient in the deep interior. For black holes and real-time problems, ingoing Eddington–Finkelstein coordinates are usually better at the horizon. A practical strategy is:

1. solve the full bulk problem in coordinates adapted to the interior;
2. convert the near-boundary expansion to Fefferman–Graham form, or at least identify the same asymptotic data;
3. compute renormalized quantities using covariant counterterms on the cutoff surface.

The counterterms are local functionals of induced fields. They do not care about the global coordinate system as long as the asymptotic structure is under control.

## Step 3: solve the near-boundary expansion

Near the boundary, the equations of motion can be solved asymptotically. This is the step where sources, local terms, logs, and response data separate.

For a scalar of mass $m$,

$$
m^2L^2=\Delta(\Delta-d),
$$

and in standard quantization the expansion has the schematic form

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}(x)+z^2\phi_{(2)}(x)+\cdots
\right)
+
z^\Delta
\left(
\phi_{(2\Delta-d)}(x)+\cdots
\right).
$$

The coefficient $\phi_{(0)}$ is the source. The coefficient $\phi_{(2\Delta-d)}$ is the first nonlocal response coefficient, up to local terms and normalization. The coefficients between them are usually determined recursively by $\phi_{(0)}$ and the boundary geometry.

For the metric in Fefferman–Graham gauge,

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)
+z^2 g_{(2)ij}(x)
+\cdots
+z^d g_{(d)ij}(x)
+z^d\log z^2\,h_{(d)ij}(x)
+\cdots .
$$

Here $g_{(0)ij}$ is the metric source. The coefficient $g_{(d)ij}$ contains the stress-tensor data, while the lower coefficients and the logarithmic coefficient are local functionals of the source. In even boundary dimension, the logarithmic term is tied to the Weyl anomaly.

For a Maxwell field in radial gauge $A_z=0$,

$$
A_i(z,x)
=
A_{(0)i}(x)
+z^{d-2}A_{(d-2)i}(x)
+\cdots,
$$

with possible logarithms in special dimensions. The leading coefficient $A_{(0)i}$ is the source for $J^i$, while the response coefficient is related to the current.

### What to write down explicitly

In a serious calculation, keep a table like this:

| Field | Source | Local recursive data | Response data | Logs? |
|---|---|---|---|---|
| $\phi$ | $\phi_{(0)}$ | $\phi_{(2)},\phi_{(4)},\ldots$ | $\phi_{(2\Delta-d)}$ | if dimensions collide |
| $A_i$ | $A_{(0)i}$ | gauge-covariant local terms | $A_{(d-2)i}$ | in some even cases |
| $g_{ij}$ | $g_{(0)ij}$ | $g_{(2)},\ldots,h_{(d)}$ | $g_{(d)ij}$ | for even $d$ |

This table prevents a very common mistake: assuming that every subleading term is a vev. Many subleading terms are fixed locally by the source.

## Step 4: impose the interior condition

Near-boundary analysis alone does not determine the state. It tells you the allowed asymptotic form and the counterterms. The response data are fixed only after imposing an interior condition.

Examples:

| Problem | Interior condition | Boundary meaning |
|---|---|---|
| Euclidean vacuum correlator | regularity in Euclidean AdS | vacuum correlator |
| Euclidean black hole | smoothness at the cigar tip | thermal equilibrium |
| Lorentzian retarded function | ingoing wave at the horizon | causal response |
| Global AdS normal modes | normalizability and regularity | CFT energy eigenstates |
| Domain wall solution | regular IR behavior or chosen endpoint | RG-flow state/vacuum |

This distinction is central:

$$
\text{near-boundary expansion determines counterterms,}
\qquad
\text{interior physics determines vevs.}
$$

Local divergences cannot depend on which state you choose. The finite response can.

## Step 5: evaluate the regulated action and variation

At finite cutoff $z=\epsilon$, evaluate the on-shell action:

$$
S_{\rm reg}[\epsilon]
=
S_{\rm bulk}^{z\ge\epsilon}
+
S_{\rm GHY}^{z=\epsilon}
$$

for gravity, with analogous boundary terms for other variational problems. More important than $S_{\rm reg}$ itself is its variation:

$$
\delta S_{\text{reg,on-shell}}
=
\int_{\Sigma_\epsilon} d^d x\,
\left(
\Pi_\phi\,\delta\phi
+
\Pi_A^i\,\delta A_i
+\frac12\Pi_\gamma^{ij}\,\delta\gamma_{ij}
+\cdots
\right).
$$

The cutoff momenta $\Pi_\phi$, $\Pi_A^i$, and $\Pi_\gamma^{ij}$ generally diverge as $\epsilon\to0$. Holographic one-point functions are not the raw momenta. They are the finite renormalized momenta after counterterms are included.

For a scalar with action

$$
S_\phi
=
\frac{\mathcal N}{2}
\int d^{d+1}x\sqrt{g}\,
\left(g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right),
$$

the on-shell variation at the cutoff takes the form

$$
\delta S_{\text{reg,on-shell}}
=
\int_{\Sigma_\epsilon} d^d x\,
\Pi_\phi\,\delta\phi,
\qquad
\Pi_\phi
=
\mathcal N\sqrt{\gamma}\,n^M\partial_M\phi,
$$

up to the sign convention for the outward normal. This is the raw radial canonical momentum. It is useful, but not yet finite.

## Step 6: add local counterterms

Counterterms are local functionals on the cutoff surface:

$$
S_{\rm ct}[\epsilon]
=
\int_{\Sigma_\epsilon} d^d x\sqrt{\gamma}\,
\mathcal L_{\rm ct}(\gamma_{ij},\phi,A_i,\nabla_i,\ldots;\epsilon).
$$

They are chosen to cancel divergences in both the action and its variation. The counterterm action must be covariant with respect to cutoff-surface diffeomorphisms and compatible with gauge symmetry, unless one is intentionally describing an anomaly.

For a scalar in standard quantization, the first counterterm has the schematic form

$$
S_{\rm ct}^{(\phi)}
=
\frac{\mathcal N}{2}
\int_{\Sigma_\epsilon} d^d x\sqrt{\gamma}\,
\frac{d-\Delta}{L}\,\phi^2
+
\text{derivative counterterms}
+
\text{log terms if needed}.
$$

The derivative counterterms involve invariants such as

$$
\gamma^{ij}\partial_i\phi\partial_j\phi,
\qquad
R[\gamma]\phi^2,
\qquad
\Box_\gamma\phi\,\Box_\gamma\phi,
$$

with coefficients fixed recursively by the near-boundary expansion. Logarithmic terms appear when the recursive solution hits a resonance. Those log terms are the holographic origin of conformal anomalies.

For pure Einstein gravity, the counterterm Lagrangian begins schematically as

$$
\mathcal L_{\rm ct}^{\rm grav}
=
\frac{1}{16\pi G_{d+1}}
\left(
\text{constant}
+
L\,R[\gamma]
+L^3\left(R_{ij}[\gamma]R^{ij}[\gamma],R[\gamma]^2\right)
+\cdots
\right),
$$

with signs depending on the Euclidean/Lorentzian and extrinsic-curvature conventions. The precise coefficients should be derived from the Hamilton–Jacobi equation or from the asymptotic expansion, not guessed.

### Minimal subtraction versus finite counterterms

Counterterms split into two conceptual groups:

$$
S_{\rm ct}
=
S_{\rm ct}^{\rm div}
+
S_{\rm ct}^{\rm finite}.
$$

The divergent part is required to define finite observables. The finite local part is a scheme choice or ensemble choice. It can change contact terms and local contributions to one-point functions, but it cannot change separated-point nonlocal data.

For example, adding

$$
S_{\rm finite}
=
\alpha\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}^2
$$

changes

$$
\langle\mathcal O\rangle
\to
\langle\mathcal O\rangle
-2\alpha\phi_{(0)}
$$

in the source convention of this course. This is not a contradiction. It is ordinary renormalization-scheme dependence.

## Step 7: take the finite limit

Define

$$
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left(S_{\rm reg}[\epsilon]+S_{\rm ct}[\epsilon]\right),
$$

and likewise define renormalized canonical momenta:

$$
\Pi_{\rm ren}
=
\lim_{\epsilon\to0}
\left(\Pi_{\rm reg}+\Pi_{\rm ct}\right)
\times
\text{appropriate rescaling to the boundary source}.
$$

The phrase “appropriate rescaling” is important. The field varied at finite cutoff is the induced cutoff field, while the CFT source is the finite coefficient in the asymptotic expansion. For a scalar,

$$
\phi(\epsilon,x)
\sim
\epsilon^{d-\Delta}\phi_{(0)}(x),
$$

so variations with respect to $\phi(\epsilon,x)$ and $\phi_{(0)}(x)$ differ by powers of $\epsilon$.

For a scalar in standard quantization, assuming a flat boundary, no logarithms, and no finite counterterms, the practical result is often written as

$$
\boxed{
\langle\mathcal O(x)\rangle
=
\mathcal N(2\Delta-d)\phi_{(2\Delta-d)}(x)
+
\text{local terms}.}
$$

The local terms are fixed by the sources and by the chosen scheme. In many simple examples with constant sources on a flat boundary, they vanish. In curved or spacetime-dependent backgrounds, they often do not.

For a conserved current, the analogous formula is

$$
\langle J^i\rangle
=
\text{finite part of the renormalized electric flux through }\Sigma_\epsilon.
$$

For the stress tensor,

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W_{\rm CFT}}{\delta g_{(0)ij}}
\approx
-
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta g_{(0)ij}}.
$$

Equivalently, it is the finite renormalized Brown–York tensor, expressed with respect to $g_{(0)ij}$.

## Step 8: obtain correlators

There are two equivalent ways to compute correlators.

The first is to differentiate the renormalized on-shell action:

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_c
=
\frac{\delta}{\delta J(y)}
\langle\mathcal O(x)\rangle_J
\bigg|_{J=0}
=
\frac{\delta^2 W}{\delta J(x)\delta J(y)}\bigg|_{J=0}.
$$

The second is to solve the linearized bulk problem and read off the linear response:

$$
\phi_{(2\Delta-d)}(k)
=
\mathcal G(k)\phi_{(0)}(k),
$$

so that

$$
G(k)
=
\mathcal N(2\Delta-d)\mathcal G(k)
+
\text{contact terms}.
$$

For Euclidean correlators, impose regularity in the Euclidean interior. For retarded Lorentzian correlators in a black-brane background, impose ingoing boundary conditions at the horizon. For advanced correlators, impose outgoing boundary conditions. For Feynman correlators, one needs the appropriate real-time contour prescription.

The shortcut

$$
G(k)
\sim
\frac{\text{response}}{\text{source}}
$$

is safe only after the counterterms and contact terms are understood.

## Step 9: check Ward identities

The last step is not optional. Ward identities are the best diagnostic that the calculation is correctly renormalized.

For scalar sources, background gauge fields, and a boundary metric, the renormalized one-point functions should obey schematic identities of the form

$$
\nabla_i\langle J^i\rangle=0
$$

for an ordinary conserved global current, and

$$
\nabla_i\langle T^{ij}\rangle
=
\langle\mathcal O\rangle\nabla^j\phi_{(0)}
+F_{(0)}^{ji}\langle J_i\rangle
+\text{anomaly terms if present}.
$$

The trace Ward identity is

$$
\langle T^i{}_i\rangle
=
(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle
+\mathcal A,
$$

where $\mathcal A$ is the Weyl anomaly, including possible matter-source contributions.

These identities are not decorative. They test whether:

- the source/vev split was correct;
- the counterterms respect the required symmetries;
- the stress tensor normalization is correct;
- logarithmic terms were handled correctly;
- finite counterterms were included consistently.

A calculation that fails the Ward identities is usually not finished.

## A minimal scalar worked example

Consider a free scalar in Euclidean $\mathrm{AdS}_{d+1}$ with metric

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+d\vec x^2\right),
$$

and action

$$
S_\phi
=
\frac{\mathcal N}{2}
\int d^{d+1}x\sqrt{g}\,
\left(g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right).
$$

Let

$$
m^2L^2=\Delta(\Delta-d),
\qquad
\Delta>\frac d2,
$$

and assume no logarithmic resonance. Near the boundary,

$$
\phi(z,x)
=
z^{d-\Delta}\phi_{(0)}(x)
+\cdots
+z^\Delta\phi_{(2\Delta-d)}(x)
+\cdots .
$$

The regulated on-shell action is a boundary term. At $z=\epsilon$, it contains divergences determined locally by $\phi_{(0)}$. The first divergence is canceled by

$$
S_{\rm ct}^{(0)}
=
\frac{\mathcal N}{2}
\int_{z=\epsilon}d^d x\sqrt{\gamma}\,
\frac{d-\Delta}{L}\phi^2.
$$

If the source depends on $x$, derivative counterterms are also required. After adding all necessary local counterterms and taking $\epsilon\to0$, the finite variation has the structure

$$
\delta S_{\rm ren}
=
-
\int d^d x\sqrt{g_{(0)}}\,
\mathcal N(2\Delta-d)\phi_{(2\Delta-d)}\,\delta\phi_{(0)}
+
\text{local variations},
$$

in the convention used here. Therefore

$$
\langle\mathcal O\rangle
=
\mathcal N(2\Delta-d)\phi_{(2\Delta-d)}
+
\text{local terms}.
$$

The response coefficient $\phi_{(2\Delta-d)}$ is not determined by the asymptotic expansion alone. In Euclidean AdS, regularity in the interior fixes it as a nonlocal functional of $\phi_{(0)}$. Differentiating that functional gives the two-point function.

This example contains the whole logic of holographic renormalization in miniature.

## A minimal Maxwell example

Take a bulk Maxwell field with action

$$
S_A
=
\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt{g}\,F_{MN}F^{MN}.
$$

In radial gauge $A_z=0$, the canonical momentum is the electric flux through the cutoff surface:

$$
\Pi_A^i
=
\frac{1}{g_{d+1}^2}\sqrt{\gamma}\,n_MF^{Mi}.
$$

The source is $A_{(0)i}$. The current is the finite renormalized electric flux:

$$
\langle J^i\rangle
\approx
-
\lim_{\epsilon\to0}
\left(\Pi_A^i+\Pi_{A,\rm ct}^i\right),
$$

with the sign again determined by the convention $W\approx -S_{\rm ren}$. In many common dimensions and backgrounds, no power-law Maxwell counterterm is needed for constant sources, but logarithmic counterterms can appear in special dimensions or for spacetime-dependent sources.

At finite density, one often writes

$$
A_t(z)
=
\mu + \cdots + a_{(d-2)t}z^{d-2}+\cdots .
$$

Then $\mu$ is the chemical potential in the grand-canonical ensemble. The coefficient $a_{(d-2)t}$ is related to the charge density. If instead you want the canonical ensemble with fixed charge density, you must Legendre transform by adding an appropriate finite boundary term.

## A minimal stress-tensor example

For an asymptotically AdS black brane, the metric near the boundary determines the stress tensor. In a flat boundary state with no scalar sources, conformal invariance implies

$$
\langle T^i{}_i\rangle=0
$$

up to anomalies. Homogeneity and isotropy imply

$$
\langle T^i{}_j\rangle
=
\operatorname{diag}(-\varepsilon,p,p,\ldots,p)
$$

in Lorentzian signature. The trace Ward identity then gives

$$
-\varepsilon+(d-1)p=0,
$$

so

$$
\varepsilon=(d-1)p.
$$

For the planar AdS black brane, holographic renormalization gives precisely this conformal equation of state. The horizon area fixes the entropy density, while the boundary stress tensor fixes the energy density and pressure. This is why thermodynamics and holographic renormalization must agree.

## Practical recipes by task

### To compute a one-point function

1. Identify the source coefficient in the near-boundary expansion.
2. Solve the bulk equations with that source and the desired interior condition.
3. Compute the regulated canonical momentum.
4. Add counterterm contributions to the momentum.
5. Rescale to variation with respect to the finite source.
6. Take $\epsilon\to0$.
7. Apply the sign convention relating $W_{\rm CFT}$ to $S_{\rm ren}$.
8. Check the relevant Ward identity.

### To compute a Euclidean two-point function

1. Work to linear order in a small source.
2. Solve the linearized Euclidean bulk equation with regular interior behavior.
3. Find the response coefficient as a function of the source in momentum space.
4. Add local contact terms from counterterms.
5. Differentiate $W$ or use the response/source kernel.
6. Fourier transform if desired.

### To compute a retarded Green's function

1. Use Lorentzian signature.
2. Choose a black-hole or black-brane background if computing thermal response.
3. Solve the linearized fluctuation equation.
4. Impose ingoing boundary conditions at the future horizon.
5. Near the boundary, identify source and response.
6. Evaluate the renormalized canonical momentum.
7. The ratio of response to source, including counterterms, gives $G_R$.
8. Poles occur when the source vanishes but the response is nonzero: these are quasinormal modes.

### To compute a stress tensor

1. Put the metric in Fefferman–Graham form near the boundary.
2. Identify $g_{(0)ij}$ and $g_{(d)ij}$.
3. Include the Gibbons–Hawking–York term.
4. Add gravitational counterterms.
5. Compute the renormalized Brown–York tensor.
6. Express the result with indices raised and lowered by $g_{(0)ij}$.
7. Check conservation and the trace Ward identity.

## Common failure modes

### Reading off a vev before renormalizing

The coefficient of a subleading term is not automatically the vev. The vev is the renormalized variational derivative of $S_{\rm ren}$. In simple flat examples these two statements collapse to a convenient shortcut. In curved, time-dependent, sourced, or anomalous examples they do not.

### Forgetting that lower coefficients can be local

In the scalar expansion, coefficients such as $\phi_{(2)}$ are often determined by derivatives of $\phi_{(0)}$. In the metric expansion, $g_{(2)ij}$ is often a local curvature functional of $g_{(0)ij}$. These are not state data.

### Treating finite counterterms as illegal

Finite local counterterms are allowed. They are scheme choices. What is not allowed is to hide physical nonlocal data inside a local scheme choice.

### Ignoring logarithms

Logarithmic terms are not optional decorations. They are forced when the asymptotic recursion resonates. They control anomalies and scale dependence.

### Mixing Euclidean and Lorentzian prescriptions

Euclidean regularity, Lorentzian ingoing boundary conditions, and normal-mode normalizability compute different objects. A beautifully renormalized calculation can still compute the wrong Green's function if the interior prescription is wrong.

### Using finite-cutoff quantities as CFT observables

A finite cutoff theory can be interesting, but it is not the same as the renormalized boundary CFT. If you quote a finite-cutoff stress tensor or current, say so explicitly.

### Dropping boundary terms too early

On shell, bulk actions often reduce to boundary terms. Those boundary terms are exactly where the generating functional lives. Do not discard them as “surface terms” unless you have already checked the variational problem.

## A debugging checklist

When a holographic-renormalization calculation goes wrong, ask these questions:

1. Did I include the boundary term required by the variational problem?
2. Did I identify the finite source, not the cutoff field?
3. Did I include all counterterms needed for a finite action and finite variation?
4. Did I include log counterterms if the boundary dimension or operator dimension requires them?
5. Did I distinguish local source-determined coefficients from response coefficients?
6. Did I impose the correct interior condition for the desired state or Green's function?
7. Did I apply the correct sign convention between $W$ and $S_{\rm ren}$?
8. Do the final one-point functions satisfy gauge, diffeomorphism, and Weyl Ward identities?
9. Are scheme-dependent local terms separated from physical nonlocal data?
10. Are the dimensions of the final answer correct?

The last check is embarrassingly effective. If

$$
[J]=d-\Delta,
\qquad
[\langle\mathcal O\rangle]=\Delta,
$$

then every term in $\langle\mathcal O\rangle$ must have dimension $\Delta$. Likewise,

$$
[\langle J^i\rangle]=d-1,
\qquad
[\langle T^{ij}\rangle]=d.
$$

Dimensional analysis catches many missing powers of $L$, $z$, $G_N$, and $g_{d+1}^2$.

## Dictionary checkpoint

The practical dictionary extracted from this unit is:

| Bulk operation | Boundary meaning |
|---|---|
| radial cutoff $z=\epsilon$ | UV regulator $\mu\sim1/\epsilon$ |
| leading asymptotic coefficient | source |
| local recursive coefficients | contact terms, counterterms, anomaly data |
| nonlocal normalizable coefficient | state/response data |
| regularity or ingoing horizon condition | choice of state or real-time Green's function |
| local cutoff counterterms | UV counterterms in the CFT generating functional |
| finite local counterterms | renormalization scheme or ensemble choice |
| renormalized canonical momentum | one-point function |
| radial constraints | Ward identities |
| logarithmic counterterms | Weyl anomaly and scale dependence |

The sentence to remember is:

$$
\boxed{
\text{A holographic observable is a finite variational derivative, not just a coefficient in an expansion.}}
$$

## Exercises

### Exercise 1: the first scalar counterterm

Let

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+\cdots
$$

in Euclidean Poincaré AdS. Ignore derivatives along the boundary. Show that the regulated scalar on-shell action has a divergence proportional to

$$
-\frac{\mathcal N}{2}\frac{d-\Delta}{L}
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\phi^2,
$$

up to the convention for the outward normal. What counterterm cancels it?

<details>
<summary><strong>Solution</strong></summary>

The scalar on-shell action is a boundary term,

$$
S_{\text{reg,on-shell}}
=
\frac{\mathcal N}{2}
\int_{z=\epsilon}d^d x\sqrt{\gamma}\,\phi\,n^M\partial_M\phi.
$$

For the cutoff surface $z=\epsilon$, the outward normal points toward decreasing $z$, so

$$
n^M\partial_M
=
-\frac{z}{L}\partial_z
$$

in the convention used here. Since

$$
\partial_z\phi
=(d-\Delta)z^{d-\Delta-1}\phi_{(0)}+
\cdots,
$$

we get

$$
n^M\partial_M\phi
=-\frac{d-\Delta}{L}z^{d-\Delta}\phi_{(0)}+
\cdots
=-\frac{d-\Delta}{L}\phi+
\cdots .
$$

Therefore the leading regulated action is

$$
S_{\text{reg,on-shell}}
=
-\frac{\mathcal N}{2}\frac{d-\Delta}{L}
\int_{z=\epsilon}d^d x\sqrt{\gamma}\,\phi^2+
\cdots .
$$

It is canceled by

$$
S_{\rm ct}^{(0)}
=
\frac{\mathcal N}{2}\frac{d-\Delta}{L}
\int_{z=\epsilon}d^d x\sqrt{\gamma}\,\phi^2.
$$

If one chooses the opposite normal or action sign convention, the displayed signs change together, but the cancellation principle is unchanged.

</details>

### Exercise 2: which data are local?

A scalar in $\mathrm{AdS}_{d+1}$ has expansion

$$
\phi
=
z^{d-\Delta}
\left(\phi_{(0)}+z^2\phi_{(2)}+\cdots\right)
+z^\Delta\phi_{(2\Delta-d)}+
\cdots .
$$

Which coefficients are determined by near-boundary analysis alone, and which coefficient requires an interior condition?

<details>
<summary><strong>Solution</strong></summary>

The source $\phi_{(0)}$ is freely specified. Coefficients such as $\phi_{(2)}$, $\phi_{(4)}$, and so on, up to the response order, are determined locally and recursively by the equations of motion in terms of $\phi_{(0)}$ and the boundary metric. The coefficient $\phi_{(2\Delta-d)}$ is not determined by local near-boundary analysis. It is fixed by the interior condition: regularity in Euclidean AdS, ingoing behavior at a Lorentzian horizon, normalizability in global AdS, or more generally by the chosen state.

</details>

### Exercise 3: a trace Ward identity check

Suppose a homogeneous isotropic state of a $d$-dimensional CFT on flat space has

$$
\langle T^i{}_j\rangle
=
\operatorname{diag}(-\varepsilon,p,p,\ldots,p)
$$

in Lorentzian signature and has no sources other than the metric. What relation between $\varepsilon$ and $p$ should the holographic stress tensor obey?

<details>
<summary><strong>Solution</strong></summary>

With no sources and no Weyl anomaly on flat space, conformal invariance implies

$$
\langle T^i{}_i\rangle=0.
$$

For the given stress tensor,

$$
\langle T^i{}_i\rangle
=-\varepsilon+(d-1)p.
$$

Thus

$$
\varepsilon=(d-1)p.
$$

This is the conformal equation of state. It is a useful check on the normalization of the holographic stress tensor for planar black branes.

</details>

### Exercise 4: finite counterterms and contact terms

Let a finite local counterterm be added to the renormalized action:

$$
S_{\rm finite}
=
\alpha\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}^2.
$$

Using $W\approx -S_{\rm ren}$, how does this change $\langle\mathcal O\rangle$? What kind of change does it induce in the two-point function?

<details>
<summary><strong>Solution</strong></summary>

The one-point function is

$$
\langle\mathcal O(x)\rangle
\approx
-\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta\phi_{(0)}(x)}.
$$

The finite counterterm contributes

$$
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm finite}}{\delta\phi_{(0)}(x)}
=2\alpha\phi_{(0)}(x).
$$

Therefore

$$
\langle\mathcal O\rangle
\to
\langle\mathcal O\rangle-2\alpha\phi_{(0)}.
$$

Differentiating once more gives a local contribution to the two-point function proportional to a delta function. Thus the finite counterterm changes contact terms and scheme-dependent local pieces, but not separated-point nonlocal data.

</details>

## Further reading

- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- I. Papadimitriou and K. Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
