---
title: "Bibliography"
description: "An annotated source guide for the Mathematical Toolkit volume, organized by QFT use case rather than by pure-math subject alone."
sidebar:
  label: "Bibliography"
  order: 998
level: Graduate
status: "Polished draft"
source: "Annotated guide to standard QFT texts, mathematics references, research reviews, and numerical-analysis sources used across the Mathematical Toolkit volume."
topics:
  - bibliography
  - references
  - source guide
  - QFT textbooks
  - mathematical physics
  - numerical methods
canonicalTopics:
  - mathematical-toolkit-bibliography
  - qft-source-guide
  - annotated-references
researchStatus:
  established:
    - "The bibliography records standard textbooks, monographs, reviews, and reference works that support the mathematical language used throughout QFT."
  active:
    - "The source guide should be maintained as pages mature, new references become canonical, and active research areas change."
---

## Summary

This bibliography is a source map for the Mathematical Toolkit volume. It is not a trophy shelf, not a ranking of books, and definitely not a dare to read everything before learning QFT. It is a practical guide to where the mathematical language of QFT is developed carefully, used physically, or extended in modern research.

The guiding principle is:

$$
\text{use QFT texts for physics judgment, mathematics texts for definitions, and reviews for modern context}.
$$

Individual pages should still include local references. This page answers the broader question: **which sources are worth keeping close while learning or checking the mathematics behind QFT?**

<figure class="doc-figure" style="--figure-width: 44rem;">

![A source map showing QFT textbooks, mathematics texts, research reviews, and computational references feeding into Mathematical Toolkit pages and local page references.](/figures/math-toolkit/bibliography-map.svg)

<figcaption>

The bibliography is a global orientation page. Local pages should cite the specific sources needed for their definitions, formulas, conventions, and caveats.

</figcaption>
</figure>

## How to use this bibliography

Use sources according to the job.

| Goal | Best source type |
|---|---|
| understand why a construction matters physically | QFT textbook or lecture notes |
| check a sign, normalization, or convention | the page convention plus the cited QFT source |
| verify a theorem or definition | mathematics textbook or monograph |
| learn a computational workflow | numerical-analysis or computational-physics text |
| understand the research frontier | review article or modern lecture notes |
| resolve a conflict between formulas | track assumptions, not authority |

A mature page should not cite ten books to support one elementary equation. It should cite enough for the reader to verify the result and understand where the conventions came from. Burying the reader under references is not scholarship; it is bibliography confetti.

## General QFT textbooks

These are the sources most useful for physics judgment, conventions, path integrals, perturbation theory, renormalization, symmetries, and examples.

### Srednicki, Quantum Field Theory

Srednicki is compact, calculation-oriented, and unusually good for checking standard perturbative QFT technology. It is especially useful for canonical scalar fields, path integrals, fermion path integrals, functional determinants, Feynman rules, renormalization, effective field theory, and spinor-helicity basics.

Use it when you want a clean computational baseline.

### Schwartz, Quantum Field Theory and the Standard Model

Schwartz is pedagogically explicit and modern in its use of effective field theory, renormalization-group thinking, gauge theory, and Standard Model calculations. It is especially useful for readers who want physical explanations tied closely to particle-physics calculations.

Use it when you want derivations that feel close to how calculations are actually done.

### Zee, Quantum Field Theory in a Nutshell

Zee is physically intuitive, broad, and conceptually generous. It is particularly helpful for path integrals, symmetry, anomalies, topology, and the “why should I care?” side of QFT. Its conventions and style differ from more austere references, so use it for intuition and then check conventions carefully.

Use it when the formalism feels dead and needs a pulse.

### Coleman, Lectures on Quantum Field Theory and Aspects of Symmetry

Coleman is a masterclass in physical reasoning. The lectures are especially valuable for symmetries, currents, solitons, instantons, large-order behavior, and the attitude that a calculation should explain something rather than merely exist.

Use Coleman when you want to know what a result is really saying.

### Weinberg, The Quantum Theory of Fields, Volumes I–III

Weinberg is the deep structural reference: representation theory, particles, fields, S-matrix logic, symmetries, renormalization, gauge theory, spontaneous symmetry breaking, and supersymmetry. It is not always the fastest first pass, but it is one of the best places to understand why QFT is constrained into its familiar form.

Use Weinberg when you want the architecture, not only the machinery.

### Zinn-Justin, Quantum Field Theory and Critical Phenomena

Zinn-Justin is indispensable for field theory as statistical mechanics, renormalization, critical phenomena, functional methods, saddle points, large-order behavior, and dimensional regularization. It is one of the natural bridges between QFT and the mathematics of probability, asymptotics, and RG.

Use it when QFT and statistical mechanics are the same beast wearing different hats.

### Peskin and Schroeder, An Introduction to Quantum Field Theory

Peskin and Schroeder remains a standard training text for particle-theory QFT, especially perturbation theory, renormalization, gauge theory, and phenomenological calculations. It is useful as a common language reference because many physicists know its conventions and examples.

Use it when you want to compare with the traditional particle-physics route.

### Itzykson and Zuber, Quantum Field Theory

Itzykson and Zuber is encyclopedic and old-school in the best sense: rich in formulas, formal methods, perturbation theory, renormalization, and diagrammatic technology. It is less gentle than modern pedagogical texts but remains a valuable reference.

Use it as a formula-rich backup source.

## Effective field theory and renormalization

### Burgess, Introduction to Effective Field Theory

Burgess is the best first specialized source for effective field theory as a way of thinking about hierarchies of scale. It is useful for dimensional analysis, power counting, matching, integrating out, Wilsonian actions, redundant operators, and why low-energy physics is predictive.

### Wilson and Kogut, The Renormalization Group and the ε Expansion

Wilson and Kogut is a foundational review for the modern renormalization group and its bridge between classical critical phenomena and QFT. It is especially important for understanding RG as a transformation on theories rather than only a collection of beta functions.

### Cardy, Scaling and Renormalization in Statistical Physics

Cardy is concise and clear on scaling, finite-size effects, universality, RG, and critical phenomena. It is useful for readers moving between statistical mechanics and field theory.

### Delamotte, An Introduction to the Nonperturbative Renormalization Group

Delamotte is a useful entry point for functional RG ideas, effective average actions, and nonperturbative approximation schemes.

## Linear algebra, tensors, and representation data

### Axler, Linear Algebra Done Right

Axler is excellent for vector spaces, linear maps, eigenvalues, dual spaces, and abstract linear algebra without determinant-first thinking. It is useful for learners who need a conceptual reset.

### Roman, Advanced Linear Algebra

Roman is broader and more reference-like, useful for tensor products, bilinear forms, canonical forms, modules, and multilinear algebra.

### Fulton and Harris, Representation Theory

Fulton and Harris is a standard reference for Lie algebras and representation theory with an eye toward geometry and physics. It is valuable for roots, weights, characters, Young diagrams, and compact Lie groups.

### Georgi, Lie Algebras in Particle Physics

Georgi is physically oriented and remains one of the most efficient sources for particle-physics representation theory, especially $SU(2)$, $SU(3)$, tensor methods, and gauge group data.

### Slansky, Group Theory for Unified Model Building

Slansky is a classic data-rich reference for Lie groups and representations used in particle theory. Use it for tables and representation data, not as a first pedagogical read.

## Analysis, distributions, and Fourier methods

### Folland, Real Analysis and Fourier Analysis and Its Applications

Folland’s real analysis text is a careful source for measure and integration; the Fourier text is useful for transform conventions, convolution, distributions, and harmonic analysis.

### Stein and Shakarchi, Fourier Analysis and Functional Analysis

The Princeton lectures are friendly, structured, and conceptually strong. They are good for Fourier series, Fourier transforms, Hilbert spaces, distributions, and spectral intuition.

### Reed and Simon, Methods of Modern Mathematical Physics

Reed and Simon is a major reference for functional analysis, Fourier methods, self-adjointness, spectral theory, and mathematical physics. It is not lightweight, but it is one of the places to check precise operator statements.

### Gelfand and Shilov, Generalized Functions

Gelfand and Shilov is a classic source for distribution theory and generalized functions. Use it when a delta-function identity or distributional boundary value needs a serious foundation.

### Hörmander, The Analysis of Linear Partial Differential Operators

Hörmander is the high-powered reference for distributions, wavefront sets, microlocal analysis, and PDEs. Most QFT readers should not start here, but many advanced singularity questions eventually point here.

### Friedlander and Joshi, Introduction to the Theory of Distributions

A focused and accessible source for distributions, test functions, distributional derivatives, Fourier transforms, and Green-function language.

## Functional analysis and spectral theory

### Hall, Quantum Theory for Mathematicians

Hall gives a readable bridge between Hilbert spaces, unbounded operators, spectral theory, and quantum mechanics. It is useful for physicists who want mathematical clarity without drowning.

### Teschl, Mathematical Methods in Quantum Mechanics

Teschl is a clear source for self-adjoint operators, Schrödinger operators, spectra, boundary conditions, and Sturm–Liouville theory.

### Simon, Trace Ideals and Their Applications

Simon is the standard reference for trace-class and Hilbert–Schmidt operators, determinant classes, and related spectral tools.

### Kato, Perturbation Theory for Linear Operators

Kato is the classic reference for perturbations of operators, spectral stability, analytic perturbation theory, and domains. It is advanced but essential for serious spectral questions.

### Gohberg, Goldberg, and Krupnik, Traces and Determinants of Linear Operators

Useful for operator determinants, trace ideals, Fredholm determinants, and infinite-dimensional linear algebra.

## Differential equations and Green functions

### Evans, Partial Differential Equations

Evans is a standard graduate PDE text. It is good for weak formulations, elliptic and parabolic estimates, Sobolev spaces, and the basic analytic structure behind Green functions.

### Strauss, Partial Differential Equations

Strauss is more approachable than Evans and gives a useful first pass through wave, heat, and Laplace equations.

### Courant and Hilbert, Methods of Mathematical Physics

A classic source for differential equations, variational methods, eigenvalue problems, special functions, and mathematical physics.

### Morse and Feshbach, Methods of Theoretical Physics

Old, broad, and still useful as a reference for Green functions, boundary-value problems, special functions, and separable PDEs.

### Arfken, Weber, and Harris, Mathematical Methods for Physicists

A broad computational reference for special functions, PDEs, vector analysis, and transforms. Good for quick lookup, less ideal for foundational precision.

## Complex analysis and analytic structure

### Ahlfors, Complex Analysis

Ahlfors is the classic compact reference for holomorphic functions, residues, analytic continuation, conformal maps, and basic Riemann-surface ideas.

### Stein and Shakarchi, Complex Analysis

A clear, modern, problem-rich introduction. Good for learners who want conceptual explanations and exercises.

### Conway, Functions of One Complex Variable

A solid reference for analytic functions, contour integration, normal families, and Riemann mapping.

### Whittaker and Watson, A Course of Modern Analysis

A classic source for special functions, elliptic functions, asymptotics, and complex analysis. Not modern in style, but still valuable.

### Eden, Landshoff, Olive, and Polkinghorne, The Analytic S-Matrix

Useful for dispersion relations, analytic structure, unitarity, crossing, and old-school S-matrix thinking.

## Special functions and exact equations

### NIST Digital Library of Mathematical Functions

The DLMF is the standard online reference for special functions. Use it for definitions, identities, branch conventions, asymptotics, and numerical notes.

### Olver, Asymptotics and Special Functions

Olver is essential for asymptotic expansions, uniform approximations, turning points, and special-function estimates.

### Andrews, Askey, and Roy, Special Functions

A reliable modern source for classical special functions, hypergeometric functions, orthogonal polynomials, and identities.

### Abramowitz and Stegun, Handbook of Mathematical Functions

A classic lookup reference. Many formulas are still useful, but modern readers should prefer DLMF for updated notation and corrections.

### Ronveaux, Heun’s Differential Equations

A specialized reference for Heun equations and their confluent forms.

### Lawden, Elliptic Functions and Applications

Useful for elliptic integrals, elliptic functions, and practical applications.

### Zagier and Apostol, modular-forms references

For modular forms, use Zagier’s expository writings for insight and Apostol or Diamond–Shurman for more systematic development.

## Lie groups, Clifford algebras, and spinors

### Hall, Lie Groups, Lie Algebras, and Representations

Hall is one of the best first mathematical references for Lie groups and Lie algebras, especially for physicists moving toward rigorous language.

### Knapp, Lie Groups Beyond an Introduction

A deeper reference for Lie theory, representation theory, and structure theory.

### Lawson and Michelsohn, Spin Geometry

The standard geometric reference for spin structures, Clifford algebras, spinor bundles, and Dirac operators.

### Porteous, Clifford Algebras and the Classical Groups

Useful for algebraic Clifford theory and the relation to classical groups.

### Penrose and Rindler, Spinors and Space-Time

A deep source for two-component spinors and spacetime geometry. Best for readers who want spinor geometry beyond particle-physics notation.

### Dreiner, Haber, and Martin, Two-Component Spinor Techniques

A practical reference for two-component spinor conventions used in supersymmetry and particle physics.

## Geometry, topology, and characteristic classes

### Nakahara, Geometry, Topology and Physics

Nakahara is a broad bridge text for physicists: manifolds, homology, cohomology, homotopy, bundles, connections, characteristic classes, monopoles, instantons, and path integrals. It is often the fastest first reference for geometry in QFT.

### Frankel, The Geometry of Physics

Frankel is excellent for differential forms, geometry, topology, Lie groups, bundles, Chern forms, electromagnetism, Dirac operators, spinors, and gauge fields. It is geometrically intuitive and particularly good for forms.

### Bott and Tu, Differential Forms in Algebraic Topology

The standard friendly source for de Rham cohomology, Čech ideas, spectral sequences, characteristic classes, and the topology of forms.

### Milnor and Stasheff, Characteristic Classes

The classic reference for Stiefel–Whitney, Chern, Pontryagin, and Euler classes. Essential when characteristic classes matter precisely.

### Kobayashi and Nomizu, Foundations of Differential Geometry

A deep reference for connections, curvature, principal bundles, and differential geometry.

### Eguchi, Gilkey, and Hanson, Gravitation, Gauge Theories and Differential Geometry

A classic physics-oriented review connecting geometry, index theory, gauge theory, and gravitational applications.

### Freed and Uhlenbeck, Instantons and Four-Manifolds

A mathematically serious source for instantons, bundles, four-manifold geometry, and gauge theory.

## Functional integrals and determinants

### Schulman, Techniques and Applications of Path Integration

A useful reference for quantum-mechanical path integrals, semiclassical approximations, and examples.

### Kleinert, Path Integrals in Quantum Mechanics, Statistics, Polymer Physics, and Financial Markets

Broad and detailed on path integrals across many contexts. Useful for examples and computational techniques.

### Zinn-Justin, Path Integrals in Quantum Mechanics

A focused source for path integrals, semiclassics, instantons, and perturbation theory in quantum mechanics.

### Marino, Instantons and Large N

Marino is a clear modern source for instantons, large-order behavior, functional determinants, large-$N$ methods, and nonperturbative QFT tools.

### Kirsten, Spectral Functions in Mathematics and Physics

A useful reference for zeta functions, heat kernels, determinants, and spectral methods.

### Vassilevich, Heat Kernel Expansion: User’s Manual

A practical review for heat-kernel coefficients, functional determinants, anomalies, and one-loop effective actions.

## Asymptotics, resurgence, and nonperturbative methods

### Bender and Orszag, Advanced Mathematical Methods for Scientists and Engineers

A standard first source for asymptotic series, steepest descent, WKB, boundary layers, and perturbation methods.

### Dingle, Asymptotic Expansions

A classic source for divergent series, late terms, and asymptotic thinking.

### Berry and Howls, hyperasymptotics and Stokes phenomena papers

Useful for the modern understanding of Stokes phenomena, exponentially small terms, and resurgence-adjacent asymptotics.

### Costin, Asymptotics and Borel Summability

A mathematical source for Borel summation, transseries, and resurgence structures.

### Dunne and Ünsal, resurgence reviews and papers

Important physics-oriented sources for resurgence, semiclassics, renormalons, and QFT applications.

### Marino, Instantons and Large N

Also belongs here: it is one of the most useful bridges from instantons and large-order perturbation theory to large-$N$ QFT.

## Algebraic and categorical language

### Etingof, Gelaki, Nikshych, and Ostrik, Tensor Categories

A standard modern reference for tensor categories, fusion categories, module categories, and categorical algebra.

### Bakalov and Kirillov, Lectures on Tensor Categories and Modular Functors

A useful source for tensor categories, modular tensor categories, and topological field theory connections.

### Turaev, Quantum Invariants of Knots and 3-Manifolds

A classic reference for modular categories, ribbon categories, and three-dimensional topological invariants.

### Mac Lane, Categories for the Working Mathematician

The foundational reference for category theory. It is not QFT-specific, but it is still the standard source for categorical grammar.

### Weibel, An Introduction to Homological Algebra

A standard reference for chain complexes, derived functors, spectral sequences, and homological algebra.

### Costello and Gwilliam, Factorization Algebras in Quantum Field Theory

A modern source for factorization algebras, observables, perturbative QFT, and local-to-global structures.

### Lurie, Higher Algebra and higher-categorical writings

Research-level references for higher categories, higher algebra, and extended field-theory language. Use with care; these are not first-pass learning texts.

## Probability, statistical tools, and random matrices

### Billingsley, Probability and Measure

A standard source for measure-theoretic probability, convergence, expectations, and probability measures.

### Kallenberg, Foundations of Modern Probability

A broad and advanced reference for probability theory. Useful when stochastic processes or convergence questions need precision.

### Feller, An Introduction to Probability Theory and Its Applications

Classic and deeply insightful, especially for random walks, generating functions, limit theorems, and probabilistic intuition.

### Simon, The $P(\phi)_2$ Euclidean (Quantum) Field Theory

A specialized constructive-field-theory reference connecting probability measures and Euclidean QFT.

### Glimm and Jaffe, Quantum Physics: A Functional Integral Point of View

A foundational source for constructive QFT and functional-integral measures.

### Mehta, Random Matrices

The classic reference for random-matrix ensembles, eigenvalue statistics, and orthogonal polynomial methods.

### Forrester, Log-Gases and Random Matrices

A modern and comprehensive reference for log gases, matrix ensembles, and spectral statistics.

### Anderson, Guionnet, and Zeitouni, An Introduction to Random Matrices

A rigorous modern source for random matrices, concentration, large deviations, and free-probability-adjacent results.

## Numerical mathematics and computational QFT tools

### Trefethen and Bau, Numerical Linear Algebra

A crisp first source for conditioning, QR, eigenvalues, singular values, and numerical stability.

### Golub and Van Loan, Matrix Computations

The comprehensive reference for numerical linear algebra, matrix factorizations, eigenproblems, and algorithmic details.

### Saad, Iterative Methods for Sparse Linear Systems

A standard source for Krylov methods, preconditioning, and sparse solvers.

### LeVeque, Finite Difference Methods for Ordinary and Partial Differential Equations

A clear reference for finite differences, consistency, stability, convergence, and PDE discretizations.

### Quarteroni, Sacco, and Saleri, Numerical Mathematics

A broad and readable source for interpolation, approximation, numerical integration, linear algebra, nonlinear solvers, and ODE/PDE methods.

### Brenner and Scott, The Mathematical Theory of Finite Element Methods

A rigorous finite-element reference for weak forms, Sobolev spaces, convergence, and elliptic problems.

### Trefethen, Spectral Methods in MATLAB

A practical and elegant source for spectral collocation, Chebyshev methods, Fourier methods, and convergence intuition.

### Newman and Barkema, Monte Carlo Methods in Statistical Physics

A practical introduction to Monte Carlo methods in statistical physics.

### Gubernatis, Kawashima, and Werner, Quantum Monte Carlo Methods

A specialized reference for quantum Monte Carlo algorithms and many-body applications.

## Conformal field theory and bootstrap sources

### Di Francesco, Mathieu, and Sénéchal, Conformal Field Theory

The standard large textbook on two-dimensional conformal field theory: Virasoro symmetry, minimal models, modular invariance, WZW models, affine Lie algebras, and many examples.

### Blumenhagen and Plauschinn, Introduction to Conformal Field Theory

A shorter modern source for two-dimensional CFT and string-theory-adjacent uses.

### Poland, Rychkov, and Vichi, The Conformal Bootstrap

A major review for conformal bootstrap theory, conformal blocks, crossing, unitarity, and numerical convex-optimization methods.

### Rychkov and Su, New Developments in the Numerical Conformal Bootstrap

A modern review of recent algorithmic and software developments in numerical bootstrap. Use for current computational context rather than basic mathematical background.

## Generalized symmetries, topology, and modern QFT reviews

### Gaiotto, Kapustin, Seiberg, and Willett, Generalized Global Symmetries

The foundational modern reference for higher-form global symmetries, extended charged operators, background fields, gauging, and anomalies.

### McGreevy, Generalized Symmetries in Condensed Matter

A useful bridge review connecting generalized symmetries to condensed-matter systems.

### Pestun et al., Localization Techniques in Quantum Field Theories

A broad review volume on supersymmetric localization, equivariant cohomology, index formulas, exact partition functions, and applications.

### Casini and Huerta, Entanglement Entropy in Free Quantum Field Theory

A useful review for entanglement entropy methods, replica ideas, real-time correlation-matrix methods, and free-field examples.

### Shifman, Advanced Topics in Quantum Field Theory

A modern advanced QFT text covering phases of gauge theories, solitons, instantons, higher-form symmetries, anomalies, and supersymmetric topics.

### Fradkin, Field Theories of Condensed Matter Physics

A broad source for condensed-matter field theory, critical phenomena, topological terms, quantum Hall physics, gauge theory, and entanglement.

### Altland and Simons, Condensed Matter Field Theory

A praxis-oriented reference for many-body field theory, functional integration, RG, disorder, response functions, topology, chaos, and nonequilibrium ideas.

## Recommended shelves by goal

### First serious graduate QFT pass

Use Schwartz or Srednicki as the main spine, Zee for intuition, Coleman for conceptual depth, and the conventions page to keep signs straight.

### Mathematical precision for QFT

Use Reed–Simon, Hall, Frankel, Nakahara, Bott–Tu, and Milnor–Stasheff. Add Lawson–Michelsohn for spin geometry and Simon for trace ideals.

### Statistical mechanics and critical phenomena

Use Wilson–Kogut, Zinn-Justin, Cardy, Polyakov, Altland–Simons, and Fradkin.

### Geometry, topology, and gauge fields

Use Nakahara, Frankel, Bott–Tu, Milnor–Stasheff, Kobayashi–Nomizu, Eguchi–Gilkey–Hanson, and Pestun et al.

### Functional determinants and semiclassics

Use Zinn-Justin, Schulman, Kleinert, Marino, Kirsten, Vassilevich, Bender–Orszag, and Dunne–Ünsal.

### Numerical QFT and computational methods

Use LeVeque, Trefethen, Golub–Van Loan, Saad, Quarteroni, Newman–Barkema, Gubernatis–Kawashima–Werner, and the bootstrap reviews when the problem is conformal bootstrap.

### Categorical and topological phases

Use Etingof–Gelaki–Nikshych–Ostrik, Bakalov–Kirillov, Turaev, Costello–Gwilliam, Gaiotto–Kapustin–Seiberg–Willett, and modern reviews on generalized symmetries.

## Citation habits for pages

A page should cite sources for three different reasons.

First, cite a source when a definition or theorem has a standard mathematical home. For example, characteristic classes should point to Milnor–Stasheff or Bott–Tu, while self-adjointness should point to Reed–Simon, Hall, or Teschl.

Second, cite a source when a convention is likely to differ across communities. Fourier transforms, gamma matrices, metric signature, curvature signs, and path-integral normalizations should never rely on reader telepathy.

Third, cite a source when the page summarizes an active research area. In that case, prefer reviews and primary papers over secondhand folklore.

A page does not need a citation for every algebraic step. If the derivation is written out and the assumptions are clear, the derivation itself is the evidence.

## How to handle conflicting conventions

When two sources differ, do not say one is wrong unless it actually is. Most convention conflicts are translations. A useful page should state:

$$
\text{our convention} \quad\longleftrightarrow\quad \text{common alternative convention}.
$$

Examples include:

| Object | Common convention conflict |
|---|---|
| metric | mostly-minus versus mostly-plus |
| Fourier transform | $e^{-ipx}$ versus $e^{+ipx}$ |
| curvature | sign of $R^\rho{}_{\sigma\mu\nu}$ |
| Lie algebra generators | Hermitian versus anti-Hermitian |
| gauge field strength | $F=dA+A\wedge A$ versus sign variants |
| gamma matrices | Clifford sign tied to metric signature |
| path integrals | Lorentzian $e^{iS}$ versus Euclidean $e^{-S_E}$ |

The best reference is useless if the convention mismatch is invisible.

## Source literacy exercises

### Exercise 1: Choosing a source

You need to verify the identity

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}
$$

for simple zeros $x_i$. Which kind of source should you check first: a QFT textbook, a distribution-theory text, or a numerical-analysis text?

<details><summary><strong>Solution</strong></summary>

A distribution-theory text is the cleanest first source because the identity is a statement about distributions and changes of variables. A QFT textbook is useful for seeing how the identity is used in phase space or constraints, but the mathematical justification belongs to distribution theory. A numerical-analysis text is not the natural source unless the question is about approximating the delta distribution computationally.

</details>

### Exercise 2: Detecting a convention mismatch

A geometry reference defines curvature by

$$
[\nabla_\mu,\nabla_\nu]V^\rho=R^\rho{}_{\sigma\mu\nu}V^\sigma,
$$

while another uses the opposite sign. What should a page do when using formulas from both?

<details><summary><strong>Solution</strong></summary>

The page should state the convention used locally and give the translation rule. It should not silently mix formulas. If a formula is imported from a source with the opposite sign convention, every occurrence of $R^\rho{}_{\sigma\mu\nu}$, Ricci curvature, scalar curvature, and characteristic-form normalization should be checked. The correct response is explicit translation, not source preference.

</details>

### Exercise 3: Avoiding bibliography confetti

A page derives the finite-dimensional Gaussian integral by completing the square. Does it need to cite five QFT books for the derivation?

<details><summary><strong>Solution</strong></summary>

No. If the derivation is shown explicitly, one or two references are enough for context or convention comparison. Overcitation can make a page harder to use. The better practice is to cite a source for the broader framework, such as Gaussian path integrals or Wick contractions, and let the written derivation carry the elementary step.

</details>

## Maintenance policy

This bibliography should evolve conservatively. Add a source when it does one of the following:

| Add a source if it | Do not add it merely because it |
|---|---|
| is a standard reference for a page’s definitions | is famous |
| clarifies a convention conflict | is on someone’s shelf |
| gives a better derivation than current sources | has a nice title |
| is a modern review of an active area | was recently posted |
| supports a numerical or computational method | mentions QFT in passing |

When a page becomes more specialized, the local references should become more specific. The top-level bibliography should remain an orientation map rather than a dumping ground.

## Version history

- **2026-06-27:** First polished draft. Adds an annotated global source guide for QFT texts, analysis, functional analysis, geometry, topology, special functions, representation theory, functional integrals, asymptotics, categorical language, probability, numerical methods, CFT, bootstrap, and generalized symmetries.
