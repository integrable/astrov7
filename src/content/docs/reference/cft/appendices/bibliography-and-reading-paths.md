---
title: "Bibliography and Reading Paths"
description: "A curated reading guide for Modern CFT for AdS/CFT, organized by course module, research goal, and technical depth."
sidebar:
  order: 7
---

A bibliography is not a trophy shelf. It is a navigation system.

The subject called “CFT for AdS/CFT” sits at the intersection of several literatures that developed with rather different instincts. The 2D CFT literature emphasizes exact solvability, Virasoro symmetry, rationality, modular invariance, and worldsheet methods. The modern higher-dimensional CFT literature emphasizes operator data, representation theory, crossing, unitarity, Lorentzian analyticity, and large-$N$ structure. The AdS/CFT literature emphasizes generating functionals, bulk boundary conditions, Witten diagrams, black holes, holographic renormalization, and emergent gravity.

The danger is not a lack of good references. The danger is reading them in the wrong order.

This appendix gives a practical reading map. It explains what each reference is good for, where it fits in the course, what to read first, what to postpone, and how to avoid the classic graduate-student trap of spending six months learning beautiful material that is not yet the bottleneck.

## The organizing principle

For this course, external reading should serve one of three purposes.

| Purpose | Question | Typical references |
|---|---|---|
| Conceptual orientation | What is the idea and why does it matter for holography? | Lecture notes, review articles, the first chapters of textbooks |
| Technical mastery | Can I actually compute with this formalism? | Problem-heavy texts, detailed derivations, examples |
| Research entry | What are the modern tools and open directions? | Reviews, TASI lectures, landmark papers |

The course itself is designed to provide the conceptual spine. The references below should be used to deepen particular sections, not to replace the logic of the course.

The minimal AdS/CFT-ready CFT package is

$$
\text{CFT data}
=
\left\{\Delta_i,\ell_i,R_i,C_{ijk}\right\}
\quad
\text{plus consistency: OPE, crossing, unitarity, Ward identities.}
$$

The minimal holographic interpretation is

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}\!\left[\phi_{\partial}=J\right],
$$

with the scalar mass-dimension relation

$$
m^2L^2=\Delta(\Delta-d).
$$

Any reading path that does not strengthen these equations should be treated as optional for the first pass.

## Reference labels used below

To make the reading paths concise, I will use the following labels.

| Label | Reference | Best use |
|---|---|---|
| DMS | P. Di Francesco, P. Mathieu, D. Senechal, *Conformal Field Theory*, Springer, 1997 | Deep 2D CFT: Virasoro, minimal models, modular invariance, WZW, cosets |
| Rychkov | S. Rychkov, *EPFL Lectures on Conformal Field Theory in $D\geq 3$ Dimensions*, SpringerBriefs, 2017; arXiv:1601.05000 | Clean modern higher-dimensional CFT foundations |
| SD | D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, arXiv:1602.07982 | Bootstrap, conformal blocks, crossing, numerical philosophy |
| PRV | D. Poland, S. Rychkov, A. Vichi, *The Conformal Bootstrap: Theory, Numerical Techniques, and Applications*, Rev. Mod. Phys. 91, 015002, 2019; arXiv:1805.04405 | Bootstrap review and reference map |
| Ginsparg | P. Ginsparg, *Applied Conformal Field Theory*, Les Houches 1988; arXiv:hep-th/9108028 | Compact 2D CFT orientation |
| Polchinski | J. Polchinski, *String Theory*, Vols. 1--2, Cambridge, 1998 | Worldsheet CFT and string background |
| AGMOO | O. Aharony, S. Gubser, J. Maldacena, H. Ooguri, Y. Oz, *Large $N$ Field Theories, String Theory and Gravity*, Phys. Rept. 323, 183, 2000; arXiv:hep-th/9905111 | Classic AdS/CFT review |
| Natsuume | M. Natsuume, *AdS/CFT Duality User Guide*, Springer, 2015; arXiv:1409.3575 | Beginner-friendly AdS/CFT after this course |
| Ammon-Erdmenger | M. Ammon, J. Erdmenger, *Gauge/Gravity Duality*, Cambridge, 2015 | Broad textbook on holography |
| Skenderis | K. Skenderis, *Lecture Notes on Holographic Renormalization*, Class. Quant. Grav. 19, 5849, 2002; arXiv:hep-th/0209067 | Holographic renormalization and one-point functions |
| RT-book | M. Rangamani, T. Takayanagi, *Holographic Entanglement Entropy*, Springer, 2017; arXiv:1609.01287 | Entanglement and RT/HRT technology |

A sensible first rule is:

> Read Rychkov and SD for modern $d>2$ CFT, DMS for exact 2D CFT, AGMOO or Natsuume for the first AdS/CFT pass, and Skenderis only when you are ready to compute renormalized correlators.

## The shortest serious reading path

This is the fastest path from the beginning of this course to being ready to read AdS/CFT papers without constantly hitting hidden CFT gaps.

### Stage 1: Operator language and Ward identities

Read course pages [1](/cft/orientation/why-cft-before-ads-cft/)-[20](/cft/correlation-functions/lorentzian-correlators/) carefully. In parallel, read:

- Rychkov, chapters/sections on conformal transformations, primary operators, two- and three-point functions.
- DMS, chapters 2--4 only as needed for QFT/stat mech background and global conformal invariance.
- SD, introductory sections on CFT data and crossing.

Goal:

$$
\mathcal O_i,
\quad
\Delta_i,
\quad
C_{ijk},
\quad
T_{\mu\nu},
\quad
J_\mu,
\quad
Z[J]
$$

should feel like the primitive objects of the subject.

### Stage 2: State-operator map, OPE, and bootstrap

Read course pages [21](/cft/radial-quantization-representations/radial-quantization/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/). In parallel, read:

- Rychkov on radial quantization and unitarity bounds.
- SD on conformal blocks and crossing.
- PRV only for orientation, not for technical implementation on a first pass.

Goal: understand why a CFT is not primarily a Lagrangian. It is a consistent operator algebra.

The basic logic is

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ijk}\,x^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0)+\cdots,
$$

and consistency of different OPE channels gives crossing.

### Stage 3: Essential 2D CFT

Read course pages [29](/cft/essential-2d-cft/complex-coordinates/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/). In parallel, read:

- DMS, chapters 5--8 for Virasoro, operator formalism, and minimal models.
- DMS, chapter 10 for modular invariance.
- DMS, chapters 13--18 only if you need current algebras, WZW models, modular invariants, or cosets.
- Ginsparg for a faster pass.

Goal: learn why 2D CFT is special without mistaking 2D CFT for all of CFT.

In two dimensions,

$$
SO(3,1)
\quad\text{enhances locally to}\quad
\text{Virasoro}\times\overline{\text{Virasoro}},
$$

and that enhancement is why exact solutions are possible.

### Stage 4: Thermal CFT, entanglement, and curved backgrounds

Read course pages [37](/cft/curved-thermal-entanglement/cylinder-and-finite-size/)-[40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/). In parallel, read:

- DMS chapter 11 for cylinder and finite-size ideas in 2D.
- Calabrese--Cardy for the classic QFT entanglement results.
- Casini--Huerta--Myers for the ball-to-hyperbolic-space map.
- RT-book for holographic entanglement.
- Skenderis when curved boundary sources and anomalies become unavoidable.

Goal: understand that AdS/CFT is not just a map between spectra. It is a map between states, sources, stress tensors, thermal physics, and entanglement.

### Stage 5: Supersymmetry, large $N$, and $\mathcal N=4$ SYM

Read course pages [41](/cft/symmetry-supersymmetry-scft/global-symmetries-and-currents/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/). In parallel, read:

- AGMOO, especially the early sections on the original duality and large-$N$ logic.
- D'Hoker--Freedman for $\mathcal N=4$ SYM and correlation functions.
- Beisert et al. for integrability orientation, if spin chains are relevant.
- Heemskerk--Penedones--Polchinski--Sully for holography from large-$N$ CFT.
- Penedones and Mellin-amplitude literature if bulk locality is the target.

Goal: connect CFT data to semiclassical bulk physics.

The practical dictionary is

$$
\begin{array}{ccl}
\text{single-trace primary} &\leftrightarrow& \text{single-particle bulk field},\\
\text{multi-trace primary} &\leftrightarrow& \text{multi-particle bulk state},\\
T_{\mu\nu} &\leftrightarrow& g_{MN},\\
J_\mu &\leftrightarrow& A_M,\\
\Delta &\leftrightarrow& m^2L^2,\\
C_T\gg 1 &\leftrightarrow& G_N/L^{d-1}\ll 1.
\end{array}
$$

## Course-module reading map

| Course module | Pages | First external companion | Deeper reading | What to postpone |
|---|---:|---|---|---|
| Orientation | [1](/cft/orientation/why-cft-before-ads-cft/)-[4](/cft/orientation/roadmap-and-references/) | AGMOO introduction; Natsuume introduction | Maldacena, GKP, Witten original papers | Holographic renormalization details |
| RG fixed points | [5](/cft/rg-fixed-points/wilsonian-rg/)-[8](/cft/rg-fixed-points/cft-data/) | DMS chapter 3; Rychkov intro | Cardy, Goldenfeld, Zinn-Justin | Long epsilon-expansion machinery |
| Conformal geometry | [9](/cft/conformal-geometry/conformal-transformations/)-[12](/cft/conformal-geometry/embedding-space/) | Rychkov; DMS chapter 4 | Costa et al. embedding-space papers | Full spinning-block technology |
| Operators and Ward identities | [13](/cft/operators-sources-ward-identities/primaries-and-descendants/)-[16](/cft/operators-sources-ward-identities/conformal-ward-identities/) | DMS chapter 2; Rychkov | Osborn--Petkou; Osborn local RG literature | General anomaly classification |
| Correlators | [17](/cft/correlation-functions/scalar-two-three-point-functions/)-[20](/cft/correlation-functions/lorentzian-correlators/) | Rychkov; SD | Costa et al.; Caron-Huot | Full Lorentzian inversion formula details |
| Radial quantization | [21](/cft/radial-quantization-representations/radial-quantization/)-[24](/cft/radial-quantization-representations/casimir-and-conformal-families/) | Rychkov; DMS chapter 6 | Mack representation theory; Minwalla | Noncompact representation theory |
| OPE and bootstrap | [25](/cft/ope-blocks-bootstrap/ope-as-operator-algebra/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/) | SD; PRV | Rattazzi et al.; El-Showk et al.; modern analytic bootstrap papers | Semidefinite-programming implementation |
| Essential 2D CFT | [29](/cft/essential-2d-cft/complex-coordinates/)-[32](/cft/essential-2d-cft/free-fields/) | DMS chapters 5--6; Ginsparg | BPZ; Friedan--Qiu--Shenker | Full RCFT classification |
| 2D CFT for strings and AdS$_3$ | [33](/cft/two-dimensional-cft-strings-ads3/minimal-models/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/) | DMS chapters 7--10, 13--18; Polchinski | Maldacena--Ooguri AdS$_3$ strings; Teschner Liouville | Advanced noncompact modular bootstrap |
| Curved/thermal/entanglement | [37](/cft/curved-thermal-entanglement/cylinder-and-finite-size/)-[40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/) | DMS chapters 10--11; RT-book | Casini--Huerta--Myers; Lewkowycz--Maldacena; Faulkner et al. | Quantum extremal surfaces |
| Symmetry and SCFT | [41](/cft/symmetry-supersymmetry-scft/global-symmetries-and-currents/)-[44](/cft/symmetry-supersymmetry-scft/conformal-manifolds/) | Wess--Bagger basics; Dolan--Osborn | Cordova--Dumitrescu--Intriligator | Full superconformal index technology |
| Large $N$ CFT | [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/) | AGMOO; Heemskerk et al. | Penedones; Fitzpatrick--Kaplan--Poland--Simmons-Duffin | Full Mellin bootstrap literature |
| $\mathcal N=4$ SYM bridge | [49](/cft/n4-sym-ads-cft-bridge/n4-sym-fields-and-symmetries/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/) | AGMOO; D'Hoker--Freedman | Beisert et al.; Minahan--Zarembo; integrability reviews | Finite-coupling integrability details |
| Appendices | [53](/cft/appendices/notation/)-[59](/cft/appendices/bibliography-and-reading-paths/) | This appendix set | The specialized references below | Anything not needed for your next calculation |

## Reading path A: the direct AdS/CFT route

This path is for a student whose main goal is to begin holography as soon as possible.

### Week 1: CFT as operator algebra

Read pages [1](/cft/orientation/why-cft-before-ads-cft/)-[8](/cft/rg-fixed-points/cft-data/) and [13](/cft/operators-sources-ward-identities/primaries-and-descendants/)-[20](/cft/correlation-functions/lorentzian-correlators/) of the course. Supplement with Rychkov sections on primaries, correlation functions, and Ward identities.

Checkpoint:

Can you explain why the CFT data

$$
\{\Delta_i,\ell_i,C_{ijk}\}
$$

is analogous to an $S$-matrix, but better adapted to a theory without asymptotic particle states?

### Week 2: Radial quantization and unitarity

Read pages [21](/cft/radial-quantization-representations/radial-quantization/)-[24](/cft/radial-quantization-representations/casimir-and-conformal-families/). Supplement with Rychkov on radial quantization and unitarity bounds.

Checkpoint:

Can you derive the scalar unitarity bound and explain why conserved currents sit at shortening thresholds?

### Week 3: OPE and crossing

Read pages [25](/cft/ope-blocks-bootstrap/ope-as-operator-algebra/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/). Supplement with SD.

Checkpoint:

Can you write the four-point function of identical scalars as a conformal-block expansion and state what crossing symmetry means?

### Week 4: Sources and the pre-dictionary

Return to pages [14](/cft/operators-sources-ward-identities/stress-tensor-and-currents/)-[16](/cft/operators-sources-ward-identities/conformal-ward-identities/) and [52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/). Read the GKP and Witten papers.

Checkpoint:

Can you explain why the CFT source $J$ is identified with the boundary value of a bulk field?

### Week 5: Large $N$

Read pages [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/). Supplement with AGMOO and Heemskerk et al.

Checkpoint:

Can you distinguish generalized free fields, single-trace operators, and double-trace operators?

### Week 6: $\mathcal N=4$ SYM

Read pages [49](/cft/n4-sym-ads-cft-bridge/n4-sym-fields-and-symmetries/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/). Supplement with the corresponding early sections of AGMOO and D'Hoker--Freedman.

Checkpoint:

Can you explain why the stress-tensor multiplet, chiral primaries, and $SU(4)_R$ representations are visible as Kaluza--Klein modes on $S^5$?

### Week 7: Thermal and entanglement preparation

Read pages [37](/cft/curved-thermal-entanglement/cylinder-and-finite-size/)-[40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/). Supplement with Natsuume and RT-book.

Checkpoint:

Can you explain why a thermal CFT state corresponds to an AdS black hole or black brane, and why entanglement entropy naturally asks for a codimension-two bulk surface?

### Week 8: First AdS/CFT computation

Read the original Maldacena, GKP, and Witten papers. Then compute the scalar two-point function from the on-shell bulk action in Euclidean AdS.

Checkpoint:

You should be able to reproduce the structure

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\propto
\frac{1}{|x|^{2\Delta}}
$$

from the bulk near-boundary behavior.

## Reading path B: full-semester CFT mastery

This is the best path for a graduate course or self-study sequence that wants the CFT foundations to be genuinely strong.

| Weeks | Course pages | External reading | Deliverable |
|---:|---|---|---|
| 1--2 | [1](/cft/orientation/why-cft-before-ads-cft/)-[8](/cft/rg-fixed-points/cft-data/) | DMS chapters 2--3; Rychkov intro | RG fixed-point summary and examples |
| 3--4 | [9](/cft/conformal-geometry/conformal-transformations/)-[16](/cft/operators-sources-ward-identities/conformal-ward-identities/) | DMS chapter 4; Rychkov conformal algebra | Ward identity derivations |
| 5--6 | [17](/cft/correlation-functions/scalar-two-three-point-functions/)-[24](/cft/radial-quantization-representations/casimir-and-conformal-families/) | Rychkov; Osborn--Petkou selections | Two-/three-point function derivation and unitarity bounds |
| 7--8 | [25](/cft/ope-blocks-bootstrap/ope-as-operator-algebra/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/) | SD; PRV selections | Conformal block/crossing mini-project |
| 9--10 | [29](/cft/essential-2d-cft/complex-coordinates/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/) | DMS chapters 5--10 | Virasoro/minimal-model/modular assignment |
| 11 | [37](/cft/curved-thermal-entanglement/cylinder-and-finite-size/)-[40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/) | RT-book; Casini--Huerta--Myers | Entanglement first-law derivation |
| 12 | [41](/cft/symmetry-supersymmetry-scft/global-symmetries-and-currents/)-[44](/cft/symmetry-supersymmetry-scft/conformal-manifolds/) | Dolan--Osborn; Cordova et al. | Shortening and BPS map |
| 13 | [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/) | Heemskerk et al.; Penedones | Large-$N$ OPE and Witten diagram map |
| 14 | [49](/cft/n4-sym-ads-cft-bridge/n4-sym-fields-and-symmetries/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/) | AGMOO; D'Hoker--Freedman | $\mathcal N=4$ SYM dictionary presentation |

This path is the best preparation for doing research in holographic CFT, not merely reading about it.

## Reading path C: exact 2D CFT and AdS$_3$/CFT$_2$

This path is for students interested in strings on AdS$_3$, black holes in three dimensions, Liouville theory, WZW models, rational CFT, or worldsheet methods.

Start with pages [29](/cft/essential-2d-cft/complex-coordinates/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/), but do not rush. Then use DMS as the main textbook.

| Topic | Course page | DMS chapters | Why it matters |
|---|---:|---|---|
| Complex coordinates and local conformal maps | [29](/cft/essential-2d-cft/complex-coordinates/) | 5 | Local conformal symmetry is infinite-dimensional in 2D |
| Stress tensor and Virasoro | [30](/cft/essential-2d-cft/stress-tensor-and-virasoro/) | 5--6 | $T(z)$ generates local conformal transformations |
| Verma modules and null states | [31](/cft/essential-2d-cft/virasoro-representations/) | 7--8 | Null states produce BPZ equations and exact correlators |
| Free fields | [32](/cft/essential-2d-cft/free-fields/) | 5--6, 9 | Bosons, fermions, ghosts, Coulomb gas, vertex operators |
| Minimal models | [33](/cft/two-dimensional-cft-strings-ads3/minimal-models/) | 7--8 | Rational solvable examples and Ising CFT |
| Modular invariance and Cardy | [34](/cft/two-dimensional-cft-strings-ads3/modular-invariance-and-cardy/) | 10 | Torus consistency and density of states |
| WZW models | [35](/cft/two-dimensional-cft-strings-ads3/current-algebras-wzw/) | 13--18 | Affine symmetry, Sugawara construction, KZ equations, cosets |
| Liouville and noncompact CFT | [36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/) | outside core DMS; use specialized reviews | Continuous spectra and noncritical strings |

The key distinction is this:

$$
\text{rational CFT}
\quad\text{has finitely many primary families,}
$$

whereas noncompact CFTs such as Liouville theory have continuous spectra. AdS$_3$ string theory often forces you into the second world, so do not assume minimal-model intuition is universal.

Recommended additional references for this path:

- P. Ginsparg, *Applied Conformal Field Theory*, arXiv:hep-th/9108028.
- J. Polchinski, *String Theory*, Vol. 1, especially the worldsheet CFT chapters.
- D. Friedan, E. Martinec, S. Shenker, *Conformal Invariance, Supersymmetry and String Theory*, Nucl. Phys. B271, 93, 1986.
- J. Teschner's review articles on Liouville theory and noncompact CFT.
- J. Maldacena and H. Ooguri, papers on strings in $\mathrm{AdS}_3$ and $SL(2,\mathbb R)$ WZW models.

## Reading path D: conformal bootstrap and holographic CFT

This path is for students who want to understand how locality and gravity emerge from consistency of CFT data.

Read pages [25](/cft/ope-blocks-bootstrap/ope-as-operator-algebra/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/) and [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/) as a single arc. Then use:

1. SD for the modern bootstrap framework.
2. PRV for the global map of numerical bootstrap.
3. Heemskerk--Penedones--Polchinski--Sully for the large-$N$ holographic logic.
4. Penedones for Mellin amplitudes.
5. Fitzpatrick--Kaplan--Poland--Simmons-Duffin and Komargodski--Zhiboedov for large-spin perturbation theory.
6. Caron-Huot for Lorentzian inversion and analyticity in spin.

The conceptual chain is

$$
\text{crossing}
\quad\Longrightarrow\quad
\text{large-spin double-trace towers}
\quad\Longrightarrow\quad
\text{bulk locality constraints}.
$$

The most important technical object is the four-point function of single-trace scalars. At leading large $N$ it is generalized free. At order $1/N^2$ one sees exchange and contact interactions:

$$
\Delta_{n,\ell}
=
\Delta_1+\Delta_2+2n+\ell+\frac{1}{N^2}\gamma_{n,
\ell}+\cdots.
$$

If you understand where the anomalous dimensions $\gamma_{n,\ell}$ come from, you are already entering the research literature.

## Reading path E: $\mathcal N=4$ SYM and integrability

For the canonical $\mathrm{AdS}_5/\mathrm{CFT}_4$ example, pages [49](/cft/n4-sym-ads-cft-bridge/n4-sym-fields-and-symmetries/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/) are the entry point.

Read in this order:

1. AGMOO for the full historical and structural overview.
2. D'Hoker--Freedman for correlation functions and supersymmetric gauge theory details.
3. Dolan--Osborn for superconformal representations and protected multiplets.
4. Kinney--Maldacena--Minwalla--Raju for the superconformal index.
5. Minahan--Zarembo for the spin-chain discovery.
6. Beisert et al. for the integrability review.

The core representation-theoretic facts are

$$
SO(6)_R\simeq SU(4)_R,
$$

and half-BPS single-trace chiral primaries have schematic form

$$
\mathcal O_p(x,Y)
=
\operatorname{Tr}\left(Y_I\Phi^I(x)\right)^p,
\qquad
Y^2=0,
$$

with

$$
\Delta=p,
\qquad
SU(4)_R\text{ representation }[0,p,0].
$$

In the bulk these match Kaluza--Klein modes on $S^5$.

## Reading path F: black holes, thermal CFT, and entanglement

This path is for students whose AdS/CFT motivation comes from quantum gravity, black holes, entropy, and information.

Start with pages [37](/cft/curved-thermal-entanglement/cylinder-and-finite-size/)-[40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/) and [52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/). Then read:

- Natsuume for thermal correlators and black brane intuition.
- AGMOO for the original black brane thermodynamics in AdS/CFT.
- RT-book for holographic entanglement entropy.
- Casini--Huerta--Myers for the ball modular Hamiltonian and hyperbolic black-hole map.
- Lewkowycz--Maldacena for generalized gravitational entropy.
- Faulkner--Lewkowycz--Maldacena for quantum corrections to holographic entanglement.
- Maldacena--Shenker--Stanford for chaos bounds.

Keep the CFT statements separate from the bulk statements. On the CFT side, the basic data are

$$
\rho_\beta=\frac{e^{-\beta H}}{Z(\beta)},
\qquad
G_R(t,\mathbf x)=-i\theta(t)\langle[\mathcal O(t,\mathbf x),\mathcal O(0)]\rangle_\beta,
$$

and

$$
S_A=-\operatorname{Tr}\rho_A\log\rho_A.
$$

Only after these are clear should one translate to black holes, horizons, quasinormal modes, and extremal surfaces.

## Annotated bibliography

The following list is curated rather than exhaustive. The point is to know what each item is for.

### Original AdS/CFT papers

**J. Maldacena, “The Large $N$ Limit of Superconformal Field Theories and Supergravity,” Adv. Theor. Math. Phys. 2, 231, 1998; arXiv:hep-th/9711200.**

The foundational paper. Read it after you know what a CFT operator, large $N$, and a chiral primary are. The paper is short but conceptually dense.

**S. Gubser, I. Klebanov, A. Polyakov, “Gauge Theory Correlators from Non-Critical String Theory,” Phys. Lett. B428, 105, 1998; arXiv:hep-th/9802109.**

One of the two papers that made the correlation-function dictionary explicit.

**E. Witten, “Anti-de Sitter Space and Holography,” Adv. Theor. Math. Phys. 2, 253, 1998; arXiv:hep-th/9802150.**

The other fundamental source-dictionary paper. This is the one to read alongside page [52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/).

### General AdS/CFT reviews and textbooks

**Aharony--Gubser--Maldacena--Ooguri--Oz, “Large $N$ Field Theories, String Theory and Gravity,” Phys. Rept. 323, 183, 2000; arXiv:hep-th/9905111.**

The classic review. Still one of the best broad introductions to the structure of the correspondence.

**M. Natsuume, *AdS/CFT Duality User Guide*, Springer, 2015; arXiv:1409.3575.**

Excellent for first computations and physical intuition, especially thermal holography.

**M. Ammon and J. Erdmenger, *Gauge/Gravity Duality*, Cambridge, 2015.**

Good as a broad reference after the first pass. More textbook-like than many reviews.

**K. Skenderis, “Lecture Notes on Holographic Renormalization,” Class. Quant. Grav. 19, 5849, 2002; arXiv:hep-th/0209067.**

Essential when you want to compute renormalized one-point functions, stress tensors, anomalies, and finite correlators from asymptotically AdS solutions.

### Modern CFT and bootstrap

**S. Rychkov, *EPFL Lectures on Conformal Field Theory in $D\geq 3$ Dimensions*, SpringerBriefs, 2017; arXiv:1601.05000.**

The cleanest first modern reference for higher-dimensional CFT. It pairs naturally with pages [9](/cft/conformal-geometry/conformal-transformations/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/).

**D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982.**

The best bridge from CFT data to crossing equations and numerical bootstrap philosophy.

**D. Poland, S. Rychkov, A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” Rev. Mod. Phys. 91, 015002, 2019; arXiv:1805.04405.**

A major review. Use it as a map of the literature rather than as your first source.

**R. Rattazzi, V. Rychkov, E. Tonni, A. Vichi, “Bounding Scalar Operator Dimensions in 4D CFT,” JHEP 0812, 031, 2008; arXiv:0807.0004.**

The modern numerical bootstrap starting point.

**S. El-Showk et al., “Solving the 3D Ising Model with the Conformal Bootstrap,” Phys. Rev. D86, 025022, 2012; arXiv:1203.6064.**

A landmark example of bootstrap precision.

### Conformal correlators and spinning operators

**H. Osborn and A. Petkou, “Implications of Conformal Invariance in Field Theories for General Dimensions,” Annals Phys. 231, 311, 1994; arXiv:hep-th/9307010.**

Classic reference for conformal constraints on current and stress-tensor correlators.

**M. Costa, J. Penedones, D. Poland, S. Rychkov, “Spinning Conformal Correlators,” JHEP 1111, 071, 2011; arXiv:1107.3554.**

Embedding-space formalism for spinning operators. Use after pages [12](/cft/conformal-geometry/embedding-space/) and [18](/cft/correlation-functions/spinning-correlators/).

**M. Costa, J. Penedones, D. Poland, S. Rychkov, “Spinning Conformal Blocks,” JHEP 1111, 154, 2011; arXiv:1109.6321.**

Technical companion for spinning conformal blocks.

### Analytic bootstrap, Lorentzian CFT, and large spin

**A. Fitzpatrick, J. Kaplan, D. Poland, D. Simmons-Duffin, “The Analytic Bootstrap and AdS Superhorizon Locality,” JHEP 1312, 004, 2013; arXiv:1212.3616.**

A key paper connecting large-spin CFT data to holographic locality.

**Z. Komargodski and A. Zhiboedov, “Convexity and Liberation at Large Spin,” JHEP 1311, 140, 2013; arXiv:1212.4103.**

Large-spin universality from crossing and unitarity.

**S. Caron-Huot, “Analyticity in Spin in Conformal Theories,” JHEP 1709, 078, 2017; arXiv:1703.00278.**

The Lorentzian inversion formula. This is a research-level tool; do not start here.

**J. Maldacena, S. Shenker, D. Stanford, “A Bound on Chaos,” JHEP 1608, 106, 2016; arXiv:1503.01409.**

Essential for thermal chaos and black-hole information discussions.

### Large $N$, Mellin amplitudes, and holographic CFT

**I. Heemskerk, J. Penedones, J. Polchinski, J. Sully, “Holography from Conformal Field Theory,” JHEP 0910, 079, 2009; arXiv:0907.0151.**

Central reference for the idea that large-$N$ CFTs with appropriate spectra reconstruct local bulk effective field theory.

**J. Penedones, “Writing CFT Correlation Functions as AdS Scattering Amplitudes,” JHEP 1103, 025, 2011; arXiv:1011.1485.**

Introduces Mellin amplitudes as an AdS/CFT analog of scattering amplitudes.

**A. Fitzpatrick and J. Kaplan, “Analyticity and the Holographic $S$-Matrix,” JHEP 1210, 127, 2012; arXiv:1111.6972.**

Useful for understanding how flat-space scattering emerges from CFT correlators.

### Two-dimensional CFT

**P. Di Francesco, P. Mathieu, D. Senechal, *Conformal Field Theory*, Springer, 1997.**

The standard 2D CFT encyclopedia. It is excellent for Virasoro symmetry, minimal models, Coulomb gas, modular invariance, finite-size scaling, Ising, WZW models, affine Lie algebras, modular invariants, fusion rules, and cosets. It is not the shortest route to higher-dimensional holographic CFT, but it is the deepest companion for pages [29](/cft/essential-2d-cft/complex-coordinates/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/).

**P. Ginsparg, “Applied Conformal Field Theory,” arXiv:hep-th/9108028.**

A compact and elegant 2D CFT introduction.

**A. Belavin, A. Polyakov, A. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” Nucl. Phys. B241, 333, 1984.**

The BPZ paper. Read after you know what Virasoro null states are.

**J. Cardy, papers and lectures on conformal invariance, finite-size scaling, and modular methods.**

Essential for the statistical-mechanics side of 2D CFT.

### WZW models, affine algebras, and cosets

**DMS chapters 13--18.**

Still the most systematic textbook treatment for the standard WZW/coset route.

**V. Kac, *Infinite-Dimensional Lie Algebras*.**

Mathematical background for affine Lie algebras. Use selectively.

**Knizhnik--Zamolodchikov original work on current algebra correlators.**

Read after the Sugawara construction and affine Ward identities are comfortable.

### Liouville and noncompact CFT

**J. Teschner, reviews and lecture notes on Liouville theory.**

Best route into modern Liouville theory and noncompact CFT.

**A. Zamolodchikov and Al. Zamolodchikov, Liouville structure constant papers.**

For exact Liouville dynamics and DOZZ structure constants.

**Maldacena--Ooguri papers on strings in $\mathrm{AdS}_3$.**

Important for the $SL(2,\mathbb R)$ WZW model and AdS$_3$ string theory.

### Supersymmetry and superconformal field theory

**J. Wess and J. Bagger, *Supersymmetry and Supergravity*.**

Classic 4D supersymmetry reference. Use for notation and basic multiplets.

**D. Freedman and A. Van Proeyen, *Supergravity*.**

A more modern and extensive supersymmetry/supergravity reference.

**F. Dolan and H. Osborn, papers on superconformal representations and correlators.**

Useful for superconformal multiplets and protected data.

**C. Cordova, T. Dumitrescu, K. Intriligator, “Multiplets of Superconformal Symmetry in Diverse Dimensions,” JHEP 1903, 163, 2019; arXiv:1612.00809.**

A systematic reference for superconformal multiplet structure.

### $\mathcal N=4$ SYM and integrability

**D'Hoker and Freedman, “Supersymmetric Gauge Theories and the AdS/CFT Correspondence,” arXiv:hep-th/0201253.**

A strong reference for $\mathcal N=4$ SYM and correlation functions.

**J. Minahan and K. Zarembo, “The Bethe-Ansatz for $\mathcal N=4$ Super Yang-Mills,” JHEP 0303, 013, 2003; arXiv:hep-th/0212208.**

The spin-chain breakthrough.

**N. Beisert et al., “Review of AdS/CFT Integrability: An Overview,” Lett. Math. Phys. 99, 3, 2012; arXiv:1012.3982.**

The integrability reference map.

**J. Kinney, J. Maldacena, S. Minwalla, S. Raju, “An Index for 4 Dimensional Super Conformal Theories,” Commun. Math. Phys. 275, 209, 2007; arXiv:hep-th/0510251.**

The standard superconformal-index starting point.

### Entanglement, thermal CFT, and holographic entropy

**P. Calabrese and J. Cardy, “Entanglement Entropy and Quantum Field Theory,” J. Stat. Mech. 0406, P06002, 2004; arXiv:hep-th/0405152.**

Classic QFT entanglement paper, especially for 2D.

**S. Ryu and T. Takayanagi, “Holographic Derivation of Entanglement Entropy from AdS/CFT,” Phys. Rev. Lett. 96, 181602, 2006; arXiv:hep-th/0603001.**

The original RT proposal.

**V. Hubeny, M. Rangamani, T. Takayanagi, “A Covariant Holographic Entanglement Entropy Proposal,” JHEP 0707, 062, 2007; arXiv:0705.0016.**

The covariant HRT extension.

**H. Casini, M. Huerta, R. Myers, “Towards a Derivation of Holographic Entanglement Entropy,” JHEP 1105, 036, 2011; arXiv:1102.0440.**

The ball modular Hamiltonian and hyperbolic-space map. Very important for page [40](/cft/curved-thermal-entanglement/entanglement-and-modular-hamiltonian/).

**A. Lewkowycz and J. Maldacena, “Generalized Gravitational Entropy,” JHEP 1308, 090, 2013; arXiv:1304.4926.**

Replica derivation of holographic entropy.

**T. Faulkner, A. Lewkowycz, J. Maldacena, “Quantum Corrections to Holographic Entanglement Entropy,” JHEP 1311, 074, 2013; arXiv:1307.2892.**

Bulk entanglement correction to RT.

### General QFT, RG, and statistical mechanics

**J. Cardy, *Scaling and Renormalization in Statistical Physics*.**

Excellent for RG and critical phenomena.

**N. Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*.**

A clear physics introduction to scaling and universality.

**J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.**

Comprehensive and technical.

**M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*.**

Good for standard perturbative QFT background.

**M. Srednicki, *Quantum Field Theory*.**

Clean modern textbook, useful for path integrals and field theory basics.

**S. Weinberg, *The Quantum Theory of Fields*.**

Deep and authoritative, but not the fastest way into CFT.

### String theory and gravity background

**J. Polchinski, *String Theory*, Vols. 1--2.**

The standard string theory reference, especially for worldsheet CFT and D-branes.

**M. Green, J. Schwarz, E. Witten, *Superstring Theory*.**

Classic and comprehensive.

**B. Zwiebach, *A First Course in String Theory*.**

Good first exposure before Polchinski.

**R. Wald, *General Relativity*.**

Best conceptual GR reference for serious readers.

**S. Carroll, *Spacetime and Geometry*.**

More accessible GR introduction.

## How to choose what to read next

A good test is to ask what kind of obstruction you are facing.

### Obstruction 1: “I do not understand what the equation means.”

Read conceptual lecture notes or textbook introductions. For CFT, use Rychkov, SD, DMS, or this course. For AdS/CFT, use Natsuume or AGMOO.

### Obstruction 2: “I understand the statement but cannot derive it.”

Read the technical chapter or original derivation. For example:

- unitarity bounds $\rightarrow$ Rychkov;
- Virasoro null states $\rightarrow$ DMS;
- conformal blocks $\rightarrow$ SD;
- holographic renormalization $\rightarrow$ Skenderis;
- RT derivation $\rightarrow$ Casini--Huerta--Myers and Lewkowycz--Maldacena.

### Obstruction 3: “I can derive it, but I do not know why it matters.”

Read a review or physics-oriented paper. Often AGMOO, Natsuume, or RT-book will help more than another derivation.

### Obstruction 4: “I want to do research.”

Pick a small class of observables, not a huge subject.

Good first research-level targets include:

- a four-point function of identical scalars;
- a thermal two-point function and its retarded continuation;
- a protected correlator in $\mathcal N=4$ SYM;
- a double-trace anomalous dimension at large spin;
- a modular-invariance constraint in 2D CFT;
- an entanglement entropy calculation for a ball or interval.

Do not begin with “I want to understand all of AdS/CFT.” That is not a project; it is a weather system.

## What to postpone on a first pass

Some topics are beautiful but should usually wait until the basic dictionary is stable.

| Postpone | Why |
|---|---|
| Full classification of rational CFTs | Wonderful, but not needed for first higher-dimensional AdS/CFT |
| ADE modular invariant classification | Important for RCFT, not central to large-$N$ holography |
| Full numerical bootstrap implementation | First understand the equations and positivity |
| Full superconformal index technology | First understand BPS shortening and protected multiplets |
| Quantum extremal surfaces | First understand RT/HRT and CFT entanglement |
| Full integrability machinery | First understand planar spin chains and the one-loop dilatation operator |
| Detailed string loop corrections in AdS | First understand large $N$, $1/N^2$, and tree-level Witten diagrams |
| General local RG and anomaly cohomology | First understand Weyl anomaly and stress-tensor Ward identities |

This is not a judgment about importance. It is triage.

## How to read original papers

Original papers are often not pedagogical because they are solving a problem that did not yet have a standardized language. Read them differently from textbooks.

For an original paper, write down four things before reading details:

1. **Input:** What assumptions are made?
2. **Output:** What new result is claimed?
3. **Observable:** What quantity is being computed or constrained?
4. **Dictionary:** In AdS/CFT terms, what is the CFT object and what is the bulk object?

For example, for the GKP/Witten prescription:

| Item | Answer |
|---|---|
| Input | A CFT with sources and a bulk theory with boundary conditions |
| Output | The generating functionals are identified |
| Observable | Correlation functions from functional derivatives |
| Dictionary | $J$ is the boundary value of $\phi$; $\mathcal O$ is dual to $\phi$ |

For the RT proposal:

| Item | Answer |
|---|---|
| Input | A spatial boundary region $A$ in a holographic CFT state |
| Output | Entanglement entropy is area of an extremal bulk surface |
| Observable | $S_A=-\operatorname{Tr}\rho_A\log\rho_A$ |
| Dictionary | Entanglement entropy $\leftrightarrow$ area in Planck units |

For the conformal bootstrap:

| Item | Answer |
|---|---|
| Input | Unitarity, OPE, conformal symmetry, crossing |
| Output | Constraints on allowed spectra and OPE coefficients |
| Observable | Four-point functions |
| Dictionary | CFT consistency $\leftrightarrow$ possible bulk theories at large $N$ |

## A minimal personal library

For a graduate student preparing for AdS/CFT, the first shelf should be small:

1. Rychkov for $d>2$ CFT foundations.
2. Simmons-Duffin for bootstrap.
3. DMS for 2D CFT.
4. AGMOO or Natsuume for AdS/CFT.
5. Skenderis for holographic renormalization.
6. RT-book for entanglement.
7. Polchinski for string theory.

Everything else can be added when a calculation demands it.

## Reading strategy by background

### If your background is general relativity

You probably understand geometry and stress tensors, but may underestimate operator algebra. Focus on:

- pages [13](/cft/operators-sources-ward-identities/primaries-and-descendants/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/);
- Rychkov;
- SD;
- large-$N$ OPE pages [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/).

The key conceptual upgrade is that bulk geometry is encoded in boundary operator data, not in a boundary metric alone.

### If your background is quantum field theory

You probably know path integrals and perturbation theory, but may overvalue Lagrangians. Focus on:

- radial quantization;
- OPE convergence;
- conformal blocks;
- bootstrap;
- generalized free fields.

The key conceptual upgrade is that a CFT can be defined nonperturbatively by its consistent operator algebra.

### If your background is string theory

You may know 2D CFT well but need higher-dimensional CFT. Focus on:

- pages [9](/cft/conformal-geometry/conformal-transformations/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/);
- Rychkov;
- SD;
- pages [45](/cft/large-n-cft/generalized-free-fields/)-[52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/).

The key conceptual upgrade is that the boundary CFT is not usually a worldsheet CFT. In $\mathrm{AdS}_5/\mathrm{CFT}_4$, the CFT is a four-dimensional gauge theory.

### If your background is condensed matter or statistical mechanics

You probably understand RG and critical exponents. Focus on:

- conformal representation theory;
- Lorentzian correlators;
- Ward identities with sources;
- large $N$ and supersymmetry.

The key conceptual upgrade is that holography uses the full operator spectrum and OPE coefficients, not just universal exponents.

## Common false shortcuts

### “I know 2D CFT, so I know CFT.”

Not quite. Two-dimensional CFT is special because of Virasoro symmetry. Higher-dimensional CFT has a finite-dimensional conformal group, but the OPE/bootstrap structure is still powerful. For AdS/CFT, higher-dimensional CFT is usually the main language.

### “I know QFT, so CFT is just QFT with $\beta=0$.”

That is a starting point, not an ending point. At a fixed point, local operators organize into conformal multiplets, correlation functions obey stronger constraints, and the OPE becomes the central dynamical structure.

### “Large $N$ just means many fields.”

For holography, large $N$ means factorization and an emergent perturbative bulk expansion. The crucial scaling is schematic:

$$
\langle \mathcal O_1\cdots \mathcal O_k\rangle_{\rm conn}
\sim
N^{2-k}
$$

for appropriately normalized single-trace operators in a matrix large-$N$ theory.

### “The AdS/CFT dictionary is just $m^2L^2=\Delta(\Delta-d)$.”

That formula is important, but it is only one line. The dictionary includes sources, states, symmetries, Ward identities, thermal ensembles, entanglement, large-$N$ counting, and operator mixing.

### “The bootstrap is only numerical.”

No. Numerical bootstrap is one powerful implementation. The conceptual bootstrap is simply associativity of the OPE plus conformal symmetry and unitarity. Analytic bootstrap, large-spin perturbation theory, and Lorentzian inversion are equally central for holography.

## Suggested capstone readings

After finishing the course, choose one of these capstone clusters.

### Capstone 1: First AdS/CFT correlator

Read GKP, Witten, and Skenderis. Compute the scalar two-point function from the Euclidean AdS on-shell action.

Deliverable:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}
$$

with $C_{\mathcal O}$ fixed by the chosen normalization.

### Capstone 2: Large-$N$ four-point function

Read Heemskerk et al. and Penedones. Study a four-point function of single-trace scalars.

Deliverable: explain how contact interactions and exchange diagrams appear as corrections to generalized free field theory.

### Capstone 3: 2D modular invariance and entropy

Read DMS chapter 10 and Cardy-related references. Derive the Cardy formula.

Deliverable:

$$
S(E)
\sim
2\pi\sqrt{\frac{c}{6}\left(L_0-\frac{c}{24}\right)}
+
2\pi\sqrt{\frac{\bar c}{6}\left(\bar L_0-\frac{\bar c}{24}\right)}.
$$

Then compare with BTZ entropy.

### Capstone 4: Entanglement first law and linearized gravity

Read Casini--Huerta--Myers and Faulkner et al. Derive the entanglement first law for a ball:

$$
\delta S_A=\delta\langle K_A\rangle.
$$

Deliverable: explain why this equation is a CFT-side precursor of gravitational equations in AdS.

### Capstone 5: $\mathcal N=4$ chiral primaries

Read D'Hoker--Freedman and Dolan--Osborn. Study half-BPS operators

$$
\mathcal O_p\in[0,p,0],
\qquad
\Delta=p.
$$

Deliverable: explain their protected dimensions and their Kaluza--Klein interpretation on $S^5$.

## Exercises

### Exercise 1: Build a six-week reading plan

You want to understand the Witten prescription for CFT correlators from AdS. You have six weeks, and you already know standard QFT but not CFT. Choose pages from this course and external references.

<details><summary><strong>Solution</strong></summary>

A good six-week plan is:

| Week | Course pages | External reading | Goal |
|---:|---|---|---|
| 1 | [1](/cft/orientation/why-cft-before-ads-cft/)-[8](/cft/rg-fixed-points/cft-data/) | Rychkov intro | Understand CFT as an RG fixed point and operator data |
| 2 | [9](/cft/conformal-geometry/conformal-transformations/)-[16](/cft/operators-sources-ward-identities/conformal-ward-identities/) | Rychkov on conformal symmetry and Ward identities | Understand primaries, stress tensor, sources |
| 3 | [17](/cft/correlation-functions/scalar-two-three-point-functions/)-[24](/cft/radial-quantization-representations/casimir-and-conformal-families/) | Rychkov on correlators and radial quantization | Understand two-/three-point functions and state-operator map |
| 4 | [25](/cft/ope-blocks-bootstrap/ope-as-operator-algebra/)-[28](/cft/ope-blocks-bootstrap/lightcone-and-large-spin/) | SD sections on OPE and blocks | Understand OPE and four-point functions |
| 5 | [45](/cft/large-n-cft/generalized-free-fields/)-[48](/cft/large-n-cft/large-n-ope/) | AGMOO large-$N$ sections | Understand generalized free fields and single-trace data |
| 6 | [52](/cft/n4-sym-ads-cft-bridge/pre-dictionary/) | GKP and Witten | Derive the source dictionary and scalar two-point function |

The minimum output is a derivation of

$$
Z_{\rm CFT}[J]
=
Z_{\rm bulk}[\phi_\partial=J]
$$

and the relation between a scalar bulk mass and CFT dimension,

$$
m^2L^2=\Delta(\Delta-d).
$$

</details>

### Exercise 2: Choose the right reference

For each problem, choose the best first reference among DMS, Rychkov, SD, Skenderis, AGMOO, and RT-book.

1. You need the Kac determinant.
2. You need the scalar unitarity bound in $d>2$.
3. You need the holographic stress tensor.
4. You need the crossing equation for scalar four-point functions.
5. You need the RT formula and its covariant extension.
6. You need the historical large-$N$ AdS/CFT overview.

<details><summary><strong>Solution</strong></summary>

1. DMS. The Kac determinant belongs to Virasoro representation theory.
2. Rychkov. The scalar unitarity bound is part of higher-dimensional conformal representation theory.
3. Skenderis. The holographic stress tensor requires holographic renormalization.
4. SD. Simmons-Duffin's TASI lectures are the best first source for crossing and conformal blocks.
5. RT-book. Rangamani--Takayanagi is the natural reference for RT/HRT.
6. AGMOO. The Aharony--Gubser--Maldacena--Ooguri--Oz review is the classic overview.

</details>

### Exercise 3: Diagnose a false reading path

A student says: “I will master all of DMS before learning AdS/CFT.” Explain when this is wise and when it is inefficient.

<details><summary><strong>Solution</strong></summary>

It is wise if the student's target is 2D CFT, rational CFT, worldsheet string theory, WZW models, cosets, modular invariance, or AdS$_3$/CFT$_2$.

It is inefficient if the target is the standard $\mathrm{AdS}_5/\mathrm{CFT}_4$ correspondence, large-$N$ CFT, conformal bootstrap, holographic renormalization, or thermal black branes. For that route, the student should learn the 2D essentials from pages [29](/cft/essential-2d-cft/complex-coordinates/)-[36](/cft/two-dimensional-cft-strings-ads3/liouville-and-noncompact-cft/) and use DMS selectively, while prioritizing higher-dimensional conformal representation theory, OPE/crossing, sources, and large-$N$ factorization.

The key distinction is

$$
\text{DMS} = \text{deep exact 2D CFT},
\qquad
\text{AdS/CFT preparation} = \text{modern CFT plus large }N.
$$

</details>

### Exercise 4: Match CFT objects to AdS/CFT reading

For each CFT object, name one AdS/CFT reference cluster that develops its bulk interpretation.

| CFT object | Bulk interpretation |
|---|---|
| $T_{\mu\nu}$ | ? |
| $J_\mu$ | ? |
| single-trace scalar $\mathcal O$ | ? |
| thermal density matrix $\rho_\beta$ | ? |
| entanglement entropy $S_A$ | ? |
| half-BPS chiral primary in $\mathcal N=4$ SYM | ? |

<details><summary><strong>Solution</strong></summary>

| CFT object | Bulk interpretation | Reference cluster |
|---|---|---|
| $T_{\mu\nu}$ | Boundary stress tensor, dual to bulk metric $g_{MN}$ | GKP/Witten, Skenderis, AGMOO |
| $J_\mu$ | Conserved current, dual to a bulk gauge field $A_M$ | GKP/Witten, AGMOO, holographic renormalization references |
| single-trace scalar $\mathcal O$ | Single-particle bulk scalar field $\phi$ | GKP/Witten, Heemskerk et al., Penedones |
| thermal density matrix $\rho_\beta$ | Black hole or black brane state | AGMOO, Natsuume |
| entanglement entropy $S_A$ | RT/HRT extremal surface area | RT original papers, RT-book, Lewkowycz--Maldacena |
| half-BPS chiral primary in $\mathcal N=4$ SYM | Kaluza--Klein mode on $S^5$ | AGMOO, D'Hoker--Freedman, Dolan--Osborn |

</details>

### Exercise 5: Design a research-entry reading stack

Your goal is to understand how large-$N$ crossing constrains local bulk effective field theory. Select five references and state the order.

<details><summary><strong>Solution</strong></summary>

A good order is:

1. Rychkov for higher-dimensional CFT basics.
2. SD for conformal blocks and crossing.
3. Heemskerk--Penedones--Polchinski--Sully for holography from large-$N$ CFT.
4. Penedones for Mellin amplitudes.
5. Fitzpatrick--Kaplan--Poland--Simmons-Duffin or Komargodski--Zhiboedov for analytic bootstrap and large-spin constraints.

A more advanced sixth reference is Caron-Huot on analyticity in spin.

The conceptual deliverable is to explain how the large-$N$ expansion of a four-point function encodes bulk exchange and contact interactions.

</details>

## Final advice

Read for structures, not trivia.

The durable structures are:

$$
\begin{array}{ccl}
\text{RG fixed point} &\Rightarrow& \text{CFT},\\
\text{conformal symmetry} &\Rightarrow& \text{kinematic correlator constraints},\\
\text{radial quantization} &\Rightarrow& \text{state-operator map},\\
\text{OPE associativity} &\Rightarrow& \text{crossing/bootstrap},\\
\text{large }N &\Rightarrow& \text{bulk perturbation theory},\\
\text{sources} &\Rightarrow& \text{boundary conditions},\\
\text{thermal states} &\Rightarrow& \text{black holes},\\
\text{entanglement} &\Rightarrow& \text{bulk geometry}.
\end{array}
$$

Once these structures are internalized, the bibliography becomes less intimidating. Every reference has a job. Pick the job you need, read the tool that solves it, and return to the CFT data.
