---
title: "Fermions and Spectral Functions"
description: "How bulk Dirac fields compute retarded fermionic Green functions, spectral densities, Fermi surfaces, and non-Fermi-liquid scaling in finite-density holography."
sidebar:
  label: "Fermions and Spectral Functions"
  order: 100
---

Bosonic fields already taught us how holography computes sources, expectation values, and retarded correlators. Fermions add a new layer. They let us ask whether a strongly coupled finite-density state has sharp fermionic excitations, Fermi surfaces, gaps, particle-hole asymmetry, or non-Fermi-liquid scaling.

The basic computation is conceptually familiar:

$$
\text{solve a bulk linear wave equation with infalling horizon condition}
\quad\Longrightarrow\quad
\text{read off source and response near the boundary}.
$$

For fermions, the bulk equation is first order, the source/response split uses radial gamma-matrix projectors, and the answer is a matrix-valued retarded Green function.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A bulk Dirac equation with infalling horizon condition determines a boundary fermion Green function and spectral function.](/figures/course/fermions-spectral-functions.svg)

<figcaption>

The holographic fermion workflow. A charged bulk spinor obeys a radial Dirac equation in the finite-density black-brane background. Infalling regularity fixes the solution in the IR, while the near-boundary source-response relation gives $G_R(\omega,k)$ and the spectral function $A(\omega,k)$.

</figcaption>
</figure>

## Why this matters

Many finite-density systems are diagnosed by their fermionic spectral function. In weakly interacting condensed matter, poles of the electron Green function identify quasiparticles and Fermi surfaces. Strongly coupled systems can have much stranger behavior: broad continua, critical scaling, incoherent metals, pseudogaps, or sharp momenta without ordinary quasiparticles.

Holography provides a controlled large-$N$ way to compute fermionic response in such states. One studies a gauge-invariant fermionic operator $\mathcal O_\psi$ in the boundary theory by introducing a charged spinor $\Psi$ in the bulk.

The key object is the retarded Green function

$$
G_R(\omega,\vec k)
=
-i\int dt\,d^{d-1}x\,
e^{i\omega t-i\vec k\cdot\vec x}
\theta(t)
\langle\{\mathcal O_\psi(t,\vec x),\overline{\mathcal O}_\psi(0)\}\rangle.
$$

The spectral function is the absorptive part:

$$
A(\omega,\vec k)
=
-2\,\operatorname{Im}\operatorname{Tr}G_R(\omega,\vec k),
$$

up to convention-dependent factors. Peaks of $A(\omega,k)$ reveal the energies and lifetimes of fermionic excitations.

## The bulk Dirac action

A standard probe fermion action is

$$
S_\Psi
=
i\int d^{d+1}x\sqrt{-g}\,
\overline\Psi
\left(\Gamma^M D_M-m\right)\Psi
+
S_{\rm bdy},
$$

where

$$
D_M
=
\partial_M+
\frac14\omega_{MAB}\Gamma^{AB}
-iqA_M.
$$

Here $m$ is the bulk spinor mass, $q$ is its charge under the bulk gauge field, and $A_M$ is the same gauge field dual to the boundary current $J^\mu$.

A useful extension adds a Pauli or dipole coupling,

$$
\Delta S_\Psi
\sim
ip\int d^{d+1}x\sqrt{-g}\,
\overline\Psi\Gamma^{MN}F_{MN}\Psi,
$$

which can strongly reshape spectral functions. We will first focus on the minimal Dirac problem.

## Spinor dimensions and near-boundary data

Near the AdS boundary, decompose the spinor using the radial gamma matrix:

$$
\Psi_\pm
=
\frac12(1\pm\Gamma^{\hat z})\Psi.
$$

For a spinor in AdS$_{d+1}$, the two independent asymptotic components behave schematically as

$$
\Psi_+
\sim
z^{d/2-mL}A(x),
\qquad
\Psi_-
\sim
z^{d/2+mL}B(x),
$$

for standard quantization and $mL\geq0$. The dual operator dimension is

$$
\Delta
=
\frac d2+mL.
$$

The coefficient $A$ is the source spinor and $B$ is the response spinor. The retarded Green function is a matrix relating them:

$$
B(\omega,k)=G_R(\omega,k)A(\omega,k).
$$

More carefully, there are gamma-matrix and boundary-term conventions. But the principle is exactly the same as for scalars: solve in the interior, expand near the boundary, and read off response over source.

For spinors with

$$
0\leq mL<\frac12,
$$

an alternate quantization is possible in which the source and response roles are exchanged. This mirrors the scalar story, but the allowed mass window differs because the spinor equation is first order.

## Dirac equation in a finite-density background

Consider a translationally invariant charged black brane:

$$
ds^2
=
-g_{tt}(z)dt^2+g_{zz}(z)dz^2+g_{xx}(z)d\vec x^{\,2},
\qquad
A=A_t(z)dt.
$$

Use a Fourier ansatz

$$
\Psi(t,\vec x,z)
=
e^{-i\omega t+i kx}
\psi_{\omega,k}(z),
$$

with momentum chosen along one spatial direction. The Dirac equation becomes a radial first-order system. Its local frequency is shifted by the electrostatic potential:

$$
\omega
\quad\longrightarrow\quad
\omega+qA_t(z),
$$

up to sign conventions. This shift is the bulk origin of finite-density fermionic response.

Near a non-extremal horizon, infalling behavior is

$$
\psi_{\omega,k}(z)
\sim
(z_h-z)^{-i\omega/(4\pi T)}
\psi_{\rm reg}
$$

in Schwarzschild-like coordinates. Imposing this condition selects the retarded Green function.

Because the Dirac equation is first order, it is often convenient to evolve ratios of spinor components rather than the components themselves. In an appropriate gamma-matrix basis, the equation can be reduced to a flow equation for a matrix $\xi(z)$, where

$$
\xi(z)
=
\frac{\text{response-like component}}{\text{source-like component}}.
$$

The boundary Green function is then obtained as

$$
G_R(\omega,k)
=
\lim_{z\to0}\,z^{-2mL}\xi(z),
$$

up to a basis-dependent matrix factor and possible contact terms.

## Spectral functions

The spectral function is

$$
A(\omega,k)
=
-2\operatorname{Im}\operatorname{Tr}G_R(\omega,k).
$$

A sharp quasiparticle pole in a weakly coupled Fermi liquid has the schematic form

$$
G_R(\omega,k)
\sim
\frac{Z}{\omega-v_F(k-k_F)+i\Gamma(\omega,k)},
$$

with $\Gamma\ll\omega$ near the Fermi surface.

Holographic finite-density states can instead produce sharp Fermi momenta with non-Fermi-liquid scaling. A Fermi momentum is identified by a pole or strong peak at

$$
\omega=0,
\qquad
k=k_F.
$$

Equivalently, at $\omega=0$ and $k=k_F$ there is a nontrivial infalling bulk solution with vanishing boundary source. This is the fermionic analogue of a quasinormal-mode condition.

## Emergent AdS$_2$ and the IR Green function

In extremal RN-AdS backgrounds, the near-horizon region is

$$
\mathrm{AdS}_2\times\mathbb R^{d-1}.
$$

From the AdS$_2$ point of view, the boundary spatial momentum $k$ is a parameter. It contributes to the effective mass of the AdS$_2$ spinor. The IR scaling exponent is schematically

$$
\nu_k
=
\sqrt{m_{\rm eff}^2(k)L_2^2-q_{\rm eff}^2}.
$$

The corresponding IR Green function scales as

$$
\mathcal G_k(\omega)
\propto
\omega^{2\nu_k},
$$

with a retarded phase fixed by the AdS$_2$ infalling condition. Matching the AdS$_2$ solution to the UV region gives a low-energy Green function near a Fermi momentum:

$$
G_R(\omega,k)
\approx
\frac{h_1}
{k-k_F-v_F^{-1}\omega-h_2\mathcal G_{k_F}(\omega)}.
$$

The constants $h_1$, $h_2$, $v_F$, and $k_F$ depend on the UV region and must be computed from the full radial problem. The nonanalytic power of $\omega$ is controlled by the IR AdS$_2$ throat.

## Fermi-liquid-like and non-Fermi-liquid regimes

The exponent $\nu_{k_F}$ controls the low-frequency self-energy.

If

$$
\nu_{k_F}>\frac12,
$$

then the linear $\omega$ term dominates over $\omega^{2\nu_{k_F}}$ at low frequency. The excitation can look relatively Fermi-liquid-like, although the full large-$N$ finite-density state is not necessarily an ordinary Landau Fermi liquid.

If

$$
\nu_{k_F}<\frac12,
$$

then the nonanalytic IR self-energy dominates. The excitation is a non-Fermi liquid: the width is not parametrically smaller than the energy in the ordinary quasiparticle sense.

If

$$
\nu_{k_F}=\frac12,
$$

one obtains marginal-Fermi-liquid-like behavior, with logarithmic structure in the low-energy Green function.

If $\nu_k$ becomes imaginary, the AdS$_2$ region exhibits log-periodic behavior. This is often called an oscillatory region and usually indicates that the naive normal phase is trying to reorganize.

## What is the boundary fermion?

The operator $\mathcal O_\psi$ is a gauge-invariant fermionic operator of the boundary CFT. It need not be an elementary electron. In top-down examples, it may be a complicated single-trace fermionic operator. In bottom-up models, it is often treated as a phenomenological probe of fermionic spectral weight.

This is why holographic fermion spectral functions are powerful but must be interpreted carefully. A peak in $A(\omega,k)$ shows that the strongly coupled theory has a fermionic excitation with momentum $k$. It does not automatically mean one has derived a microscopic electron Green function of a real material.

## Probe approximation and charge fractionalization

Most introductory calculations treat the Dirac field as a probe. This means the fermion diagnoses the state but does not source the background geometry.

At finite density, the background charge may be carried by the horizon, by charged bosonic hair, by explicit charged matter, or by a fermion fluid. Probe fermions can reveal sharp Fermi momenta even when the charge sourcing the geometry is not carried by those probe fermions. This is one reason holographic finite-density phases are often described as fractionalized: part of the charge is hidden behind the horizon from the point of view of gauge-invariant low-energy quasiparticles.

Backreacted fermion systems, such as electron stars or Dirac-hair black holes, are richer and more difficult. The probe calculation is the right first step because it isolates the Green-function dictionary.

## Pauli couplings and zeros

The minimal Dirac action is not the most general effective action. A commonly studied correction is a dipole or Pauli coupling:

$$
S_{\rm Pauli}
\sim
ip\int d^{d+1}x\sqrt{-g}\,
\bar\Psi\Gamma^{MN}F_{MN}\Psi.
$$

Such terms can shift spectral weight, move Fermi momenta, and produce zeros of the Green function. Poles and zeros are both meaningful: poles indicate strong response to a source, while zeros indicate suppressed response.

The lesson is that holographic spectral functions are sensitive to bulk effective couplings. A bottom-up fermion model is not uniquely defined until the effective action, boundary conditions, and quantization are specified.

## Fermions in a superconducting background

One can also study probe fermions in the condensed background of the previous page. If the bulk action contains a gauge-invariant Yukawa or Majorana-like coupling between the scalar and the fermion, the condensate can open a gap in the fermionic spectral function.

A schematic interaction is

$$
S_{\rm Yukawa}
\sim
\int d^{d+1}x\sqrt{-g}\,
\eta\,\Psi^T C\Gamma\Psi\,\Phi+\mathrm{h.c.},
$$

where $\Phi$ is the charged scalar. Gauge invariance requires the charges to match. This setup gives a holographic analogue of pairing: the condensate mixes particle and hole sectors and can gap the Fermi surface.

The analogy is structural. It does not mean the minimal model has derived a BCS pairing mechanism.

## Numerical workflow

A practical spectral-function computation usually follows this route:

1. choose a charged black-brane background;
2. choose bulk spinor parameters $m$, $q$, and possible Pauli couplings;
3. fix gamma matrices and projectors;
4. solve the radial Dirac equation with infalling horizon behavior;
5. extract the response/source matrix at the boundary;
6. compute

   $$
   A(\omega,k)=-2\operatorname{Im}\operatorname{Tr}G_R(\omega,k);
   $$

7. scan over $(\omega,k)$ to find peaks, poles, gaps, or zeros.

Because the Dirac equation is first order, this is often numerically simpler than solving coupled gravitational perturbation equations. The interpretation, however, is subtle.

## Dictionary checkpoint

| Boundary object | Bulk object |
|---|---|
| fermionic operator $\mathcal O_\psi$ | bulk Dirac field $\Psi$ |
| source spinor | leading radial spinor component |
| response spinor | subleading radial spinor component |
| retarded fermion Green function | response/source matrix with infalling horizon condition |
| spectral function $A(\omega,k)$ | imaginary part of boundary Green function |
| Fermi momentum $k_F$ | source-free infalling solution at $\omega=0$ |
| non-Fermi self-energy | AdS$_2$ IR Green function $\mathcal G_k(\omega)$ |
| gap from condensate | fermion mixing in a hairy background |

## Common confusions

### “The bulk fermion is an electron.”

Not generally. It is dual to a gauge-invariant fermionic operator. In a phenomenological model, one may interpret this operator as electron-like, but that is an additional modeling assumption.

### “Every sharp peak is a stable quasiparticle.”

No. A peak can indicate strong spectral weight, but the width and scaling determine whether the excitation is long-lived. Holographic non-Fermi liquids often have sharp Fermi momenta without ordinary Landau quasiparticles.

### “The horizon itself is the Fermi surface.”

No. A charged horizon represents deconfined or fractionalized charge in the large-$N$ state. Probe-fermion Fermi surfaces are diagnosed by poles of fermionic Green functions.

### “The exponent $\nu_k$ is a UV scaling dimension.”

No. It is an infrared scaling exponent associated with the emergent AdS$_2$ region. The UV operator dimension is controlled by the asymptotic AdS$_{d+1}$ mass $mL$.

### “The spectral function alone identifies the full phase.”

No. Spectral functions are diagnostic probes. To identify a phase, one also needs thermodynamics, symmetry realization, charge distribution, transport, and stability.

## Exercises

### Exercise 1: Spinor dimension

For a Dirac field in AdS$_{d+1}$ with $mL=1/4$, what is the standard-quantization dimension of the dual fermionic operator?

<details>
<summary><strong>Solution</strong></summary>

In standard quantization,

$$
\Delta=\frac d2+mL.
$$

Therefore

$$
\Delta=\frac d2+\frac14.
$$

For example, in a $d=3$ boundary theory,

$$
\Delta=\frac32+\frac14=\frac74.
$$

</details>

### Exercise 2: Why infalling boundary conditions?

Why do infalling horizon boundary conditions compute the retarded Green function?

<details>
<summary><strong>Solution</strong></summary>

A retarded response describes a disturbance sourced at the boundary whose effect propagates into the system with causal boundary conditions. In the bulk, the black-hole horizon absorbs perturbations. The infalling condition says that near the future horizon the wave travels into the horizon rather than emerging from it. The outgoing condition would correspond to advanced or non-causal response. Thus the infalling solution is the Lorentzian bulk implementation of retarded boundary conditions.

</details>

### Exercise 3: Fermi momentum as a normal mode

Explain why a Fermi momentum can be identified by a source-free infalling solution at $\omega=0$.

<details>
<summary><strong>Solution</strong></summary>

The retarded Green function is a response/source ratio. A pole occurs when the response remains nonzero while the source coefficient vanishes. This is the same logic as a normal mode or quasinormal mode: one has a nontrivial solution satisfying the interior condition and no external source at the boundary. If such a pole occurs at $\omega=0$ and $k=k_F$, the spectral function has low-energy fermionic weight at a definite momentum. This is interpreted as a holographic Fermi surface.

</details>

### Exercise 4: AdS$_2$ scaling

Suppose

$$
\mathcal G_k(\omega)\propto\omega^{2\nu_k}
$$

and

$$
G_R(\omega,k)
\approx
\frac{h_1}
{k-k_F-v_F^{-1}\omega-h_2\omega^{2\nu_{k_F}}}.
$$

Why does $\nu_{k_F}<1/2$ lead to non-Fermi-liquid behavior?

<details>
<summary><strong>Solution</strong></summary>

If $\nu_{k_F}<1/2$, then $2\nu_{k_F}<1$. As $\omega\to0$, the term $\omega^{2\nu_{k_F}}$ decays more slowly than the linear term $\omega$. Thus the nonanalytic IR self-energy dominates the denominator. The excitation width is not parametrically smaller than its energy in the ordinary Landau-quasiparticle way, giving non-Fermi-liquid behavior.

</details>

## Further reading

- N. Iqbal and H. Liu, [Real-time response in AdS/CFT with application to spinors](https://arxiv.org/abs/0903.2596).
- H. Liu, J. McGreevy, and D. Vegh, [Non-Fermi liquids from holography](https://arxiv.org/abs/0903.2477).
- T. Faulkner, H. Liu, J. McGreevy, and D. Vegh, [Emergent quantum criticality, Fermi surfaces, and AdS$_2$](https://arxiv.org/abs/0907.2694).
- T. Faulkner, N. Iqbal, H. Liu, J. McGreevy, and D. Vegh, [From black holes to strange metals](https://arxiv.org/abs/1003.1728).
- M. Cubrovic, J. Zaanen, and K. Schalm, [String Theory, Quantum Phase Transitions and the Emergent Fermi Liquid](https://arxiv.org/abs/0904.1993).
- H. Liu, [Lectures on holographic non-Fermi liquids and quantum phase transitions](https://arxiv.org/abs/1202.5225).
