---
title: "Chiral Primaries and Protected Correlators"
description: "Half-BPS operators, protected data, and the Kaluza-Klein dictionary for N=4 SYM."
sidebar:
  order: 2
---

## Goal

This page explains the protected scalar operators of $4d$ $\mathcal N=4$ super-Yang--Mills theory and why they are the cleanest entry point into the concrete AdS/CFT dictionary. The central objects are the half-BPS single-trace operators

$$
\mathcal O_p(x,Y)\sim \mathrm{Tr}\big(Y\cdot \Phi(x)\big)^p,
\qquad
Y^2=0,
$$

where $\Phi_I$, $I=1,\ldots,6$, are the six real adjoint scalars and $Y^I$ is an auxiliary null polarization vector for $SO(6)_R$. These operators sit in the $SU(4)_R$ representation $[0,p,0]$, have protected scaling dimension

$$
\Delta=p,
$$

and are dual to Kaluza--Klein scalar modes of type IIB string theory on $\mathrm{AdS}_5\times S^5$.

A small warning about terminology: in $4d$ $\mathcal N=4$ SYM, the phrase **chiral primary** usually means a superconformal primary in a BPS multiplet, especially a half-BPS multiplet. It does **not** mean a holomorphic field in the $2d$ CFT sense.

## Why chiral primaries matter for AdS/CFT

In the abstract CFT language developed earlier, a CFT is specified by its operator spectrum and OPE coefficients. In a generic interacting CFT, very little of this data is exactly known. $\mathcal N=4$ SYM is special because supersymmetry protects a distinguished sector.

The protected half-BPS sector gives us:

1. exact operator dimensions at all values of the Yang--Mills coupling,
2. sharply defined $SU(4)_R\simeq SO(6)_R$ representation labels,
3. low-point correlators that can often be computed at weak coupling and compared directly with supergravity,
4. a clean map to Kaluza--Klein modes on $S^5$.

The reason this sector is so useful is not that it contains all the dynamics. It absolutely does not. Rather, it gives a protected anchor around which the unprotected dynamics is organized. The stress-tensor multiplet, the supergravity multiplet, the first nontrivial four-point functions, and the standard AdS/CFT tests all begin here.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 55rem;">

![Half-BPS chiral primaries and the Kaluza-Klein dictionary](/figures/cft/chiral-primaries-kk-dictionary.svg)

<figcaption>

Half-BPS scalar primaries in $\mathcal N=4$ SYM are symmetric traceless $SO(6)_R$ operators in $[0,p,0]$ with protected dimension $\Delta=p$. Under AdS/CFT they match scalar spherical harmonics of degree $p$ on $S^5$ and Kaluza--Klein scalar fields in $\mathrm{AdS}_5$ with $m^2L^2=p(p-4)$.

</figcaption>
</figure>

## The six scalars and $SO(6)_R$

The elementary fields of $\mathcal N=4$ SYM include six real adjoint scalars

$$
\Phi_I(x)=\Phi_I^a(x)T^a,
\qquad I=1,\ldots,6,
$$

transforming in the vector representation $\mathbf 6$ of $SO(6)_R$. Since

$$
SO(6)_R \simeq SU(4)_R,
$$

this same representation is also the antisymmetric representation $\mathbf 6$ of $SU(4)_R$.

The scalars have classical scaling dimension one. In the interacting theory, individual elementary fields are not gauge-invariant operators, so they are not themselves CFT observables. Gauge-invariant scalar local operators are built from traces such as

$$
\mathrm{Tr}(\Phi_I\Phi_J),
\qquad
\mathrm{Tr}(\Phi_I\Phi_J\Phi_K),
\qquad
\mathrm{Tr}(\Phi_I\Phi_J)\mathrm{Tr}(\Phi_K\Phi_L),
$$

and so on. The half-BPS operators are special linear combinations of such objects.

For a single trace of length $p$, the most important operator is the symmetric traceless product

$$
\mathcal O_p^{I_1\cdots I_p}(x)
=\mathcal N_p\,\mathrm{Tr}\big(\Phi^{(I_1}\cdots \Phi^{I_p)}\big)(x)-\text{traces},
$$

where $\mathcal N_p$ is a normalization constant and “traces” means contractions with $\delta^{IJ}$. In $SO(6)_R$ language, this is a rank-$p$ symmetric traceless tensor. In $SU(4)_R$ Dynkin-label notation, it belongs to

$$
[0,p,0].
$$

For $SU(N)$ gauge group, the $p=1$ single-trace operator vanishes because $\mathrm{Tr}\,\Phi_I=0$. The first nontrivial single-trace chiral primary is therefore $p=2$.

## Null polarization vectors

Writing all $SO(6)_R$ indices explicitly quickly becomes painful. A standard trick is to introduce an auxiliary complex vector $Y^I$ satisfying

$$
Y\cdot Y \equiv \delta_{IJ}Y^IY^J=0.
$$

Then define

$$
\mathcal O_p(x,Y)
=\mathcal N_p\,Y_{I_1}\cdots Y_{I_p}\mathcal O_p^{I_1\cdots I_p}(x).
$$

Because $Y^2=0$, any trace term proportional to $\delta^{IJ}$ drops out. Thus we can write the same operator compactly as

$$
\mathcal O_p(x,Y)
=\mathcal N_p\,\mathrm{Tr}\big(Y\cdot \Phi(x)\big)^p,
\qquad
Y^2=0.
$$

This formula is not saying that $Y$ is a physical field. It is a book-keeping device. The operator is homogeneous of degree $p$ in $Y$, so the power of $Y$ keeps track of the $SO(6)_R$ representation.

We will often use the shorthand

$$
Y_{ij}=Y_i\cdot Y_j,
\qquad
x_{ij}=x_i-x_j.
$$

## The basic example: the $20'$ operator

For $p=2$, the chiral primary is

$$
\mathcal O_2^{IJ}(x)
=\mathcal N_2\,\mathrm{Tr}\left(\Phi^I\Phi^J-\frac{1}{6}\delta^{IJ}\Phi^K\Phi^K\right)(x).
$$

This is symmetric and traceless in $I,J$, so it transforms in the $SO(6)_R$ representation

$$
\mathbf{20}'=[0,2,0].
$$

This operator is the superconformal primary of the stress-tensor multiplet. The multiplet contains, among other operators, the $SO(6)_R$ currents $J_\mu^{IJ}$, the supercurrents, and the stress tensor $T_{\mu\nu}$. This is one of the most important multiplets in the whole subject: on the AdS side, it is dual to the massless graviton multiplet of $5d$ $\mathcal N=8$ gauged supergravity obtained from type IIB supergravity on $S^5$.

A useful hierarchy is therefore:

$$
\mathcal O_2^{IJ}
\quad\text{is not itself }T_{\mu\nu},
\qquad
\mathcal O_2^{IJ}\quad\text{generates the multiplet containing }T_{\mu\nu}.
$$

This distinction matters. The scalar primary has $\Delta=2$ and lies in $[0,2,0]$; the stress tensor has $\Delta=4$, spin $2$, and is an $SO(6)_R$ singlet, but both belong to the same protected supermultiplet.

## Superconformal shortening

The full symmetry algebra of $\mathcal N=4$ SYM is

$$
\mathfrak{psu}(2,2|4),
$$

whose bosonic subalgebra is

$$
\mathfrak{so}(4,2)\oplus \mathfrak{su}(4)_R.
$$

A local operator is a superconformal primary if it is annihilated by all special conformal generators $K_\mu$ and all special supersymmetry generators $S$. Acting with the Poincare supercharges $Q$ and $\bar Q$ builds the rest of the supermultiplet.

A long multiplet has no additional null states. Its dimension is not fixed by representation theory and can vary continuously with the exactly marginal coupling $\tau$. A BPS multiplet is shorter because some of the $Q$'s annihilate the primary. This shortening forces the dimension to saturate a unitarity bound.

For the half-BPS scalar primaries relevant here,

$$
\boxed{\mathcal O_p\in [0,p,0],\qquad \Delta=p.}
$$

This equality is not a perturbative accident. It is a representation-theoretic statement. The operator cannot acquire an anomalous dimension without leaving its shortened representation. But it cannot continuously leave that representation unless the multiplet recombines with other multiplets in a way allowed by the algebra. For these half-BPS primaries, the shortening is robust.

This is why the operator

$$
\mathrm{Tr}(Y\cdot \Phi)^p
$$

is a much safer object than a generic single-trace operator such as

$$
\mathrm{Tr}(\Phi_I\Phi_I),
$$

which is an $SO(6)_R$ singlet and is not protected in the same way. In fact, the naive singlet scalar belongs to the Konishi multiplet, whose dimension is coupling-dependent.

## Chiral primaries versus the Konishi operator

The contrast with the Konishi operator is worth making explicit. The schematic Konishi primary is

$$
\mathcal K(x)=\mathrm{Tr}\big(\Phi_I\Phi_I\big)(x)+\cdots,
$$

where the dots indicate the full supersymmetric completion and possible scheme-dependent mixing. It is an $SU(4)_R$ singlet. It is not BPS. Its scaling dimension is

$$
\Delta_{\mathcal K}=2+\gamma_{\mathcal K}(\lambda,N),
$$

where $\lambda=g_{\mathrm{YM}}^2N$ is the 't Hooft coupling. At weak coupling $\gamma_{\mathcal K}$ can be computed perturbatively. At strong coupling and large $N$, the Konishi operator is dual not to a light supergravity field but to a massive string state, so its dimension grows parametrically like a string mass in AdS units.

By contrast, for the half-BPS operator,

$$
\Delta_{\mathcal O_p}=p
$$

at weak coupling, strong coupling, finite coupling, and in the planar or nonplanar theory. That is the meaning of protection.

## Two-point functions

Conformal symmetry and $SO(6)_R$ covariance fix the two-point function of normalized half-BPS scalar primaries to be

$$
\boxed{
\left\langle \mathcal O_p(x_1,Y_1)\mathcal O_q(x_2,Y_2)\right\rangle
=\delta_{pq}\,\frac{(Y_{12})^p}{(x_{12}^2)^p}.
}
$$

This formula assumes a convenient unit normalization for the operators. Other normalizations differ by constants multiplying each operator.

The structure is easy to understand. The spacetime denominator is fixed by the scaling dimensions $\Delta=p=q$. The numerator must carry $p$ powers of $Y_1$ and $p$ powers of $Y_2$. The only available $SO(6)_R$ invariant is $Y_1\cdot Y_2$, so the numerator is $(Y_{12})^p$.

The condition $p=q$ is representation theory: a two-point function pairs an operator only with another operator in the conjugate representation. The representation $[0,p,0]$ is self-conjugate, but different values of $p$ are inequivalent.

## Three-point functions

The three-point function of scalar conformal primaries is fixed by conformal symmetry up to an OPE coefficient. For half-BPS operators, $SO(6)_R$ covariance fixes the basic polarization dependence as well. Define

$$
\alpha_{12}=\frac{p_1+p_2-p_3}{2},
\qquad
\alpha_{23}=\frac{p_2+p_3-p_1}{2},
\qquad
\alpha_{13}=\frac{p_1+p_3-p_2}{2}.
$$

When these numbers are nonnegative integers, the standard three-point structure is

$$
\boxed{
\begin{aligned}
&\left\langle
\mathcal O_{p_1}(x_1,Y_1)
\mathcal O_{p_2}(x_2,Y_2)
\mathcal O_{p_3}(x_3,Y_3)
\right\rangle
\\[3pt]
&\qquad =
C_{p_1p_2p_3}
\frac{
Y_{12}^{\alpha_{12}}
Y_{23}^{\alpha_{23}}
Y_{13}^{\alpha_{13}}
}{
(x_{12}^2)^{\alpha_{12}}
(x_{23}^2)^{\alpha_{23}}
(x_{13}^2)^{\alpha_{13}}
}.
\end{aligned}
}
$$

The powers are not arbitrary. At point $1$, the numerator contains

$$
\alpha_{12}+\alpha_{13}=p_1
$$

powers of $Y_1$, and similarly at points $2$ and $3$. The denominator has the usual scalar CFT exponents because $\Delta_i=p_i$.

The coefficient $C_{p_1p_2p_3}$ is part of the protected CFT data. With a fixed normalization convention, the two- and three-point functions of half-BPS operators are protected. This is one of the classic quantitative tests of AdS/CFT: compute the same coefficient at weak coupling in free SYM and at strong coupling from a cubic coupling in supergravity.

There are finite-$N$ subtleties because single-trace and multi-trace operators with the same quantum numbers can mix. At large $N$, the single-particle interpretation is cleanest. At finite $N$, one should define an orthonormal basis of protected operators before quoting numerical OPE coefficients.

## Extremal and near-extremal correlators

A three-point function is called **extremal** if

$$
p_3=p_1+p_2
$$

up to a relabeling of the operators. In that case

$$
\alpha_{12}=0,
\qquad
\alpha_{23}=p_2,
\qquad
\alpha_{13}=p_1.
$$

The correlator becomes

$$
\left\langle
\mathcal O_{p_1}(x_1,Y_1)
\mathcal O_{p_2}(x_2,Y_2)
\mathcal O_{p_1+p_2}(x_3,Y_3)
\right\rangle
\propto
\frac{Y_{23}^{p_2}Y_{13}^{p_1}}{(x_{23}^2)^{p_2}(x_{13}^2)^{p_1}}.
$$

Extremal and near-extremal correlators have special nonrenormalization properties and special behavior in supergravity. They are delicate because some bulk cubic couplings vanish while the corresponding AdS integrals diverge, leaving a finite answer after the correct limiting procedure. The CFT statement is simpler: protected operators can have protected correlators, but the way this protection is realized in AdS variables may require care.

## What is protected, and what is not

It is tempting to say “BPS means exactly solvable.” That is too strong. The correct statement is more refined.

Protected:

- the dimensions of half-BPS primaries $\mathcal O_p$,
- their $SU(4)_R$ representation labels,
- the existence of their short multiplets,
- two-point functions after choosing normalization,
- many low-point OPE coefficients, especially the three-point functions of half-BPS operators.

Not fully protected:

- generic four-point functions of half-BPS operators,
- anomalous dimensions of long multiplets appearing in their OPE,
- OPE coefficients involving long multiplets,
- non-BPS single-trace operators such as the Konishi operator,
- finite-$N$ mixing questions unless a precise protected basis is chosen.

The four-point function of the stress-tensor multiplet is the canonical example. The external operators are protected, but their OPE contains long unprotected multiplets. Therefore the four-point function contains dynamical information. In fact, this is one of the most important observables in the modern conformal bootstrap and in precision AdS/CFT.

## Four-point functions and the protected anchor

For four identical half-BPS operators, conformal symmetry gives spacetime cross-ratios

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2},
$$

and $SO(6)_R$ gives analogous polarization cross-ratios, for example

$$
\sigma=\frac{Y_{12}Y_{34}}{Y_{13}Y_{24}},
\qquad
\tau=\frac{Y_{14}Y_{23}}{Y_{13}Y_{24}}.
$$

A four-point function such as

$$
\left\langle
\mathcal O_2(x_1,Y_1)
\mathcal O_2(x_2,Y_2)
\mathcal O_2(x_3,Y_3)
\mathcal O_2(x_4,Y_4)
\right\rangle
$$

is constrained by superconformal Ward identities but is not completely fixed. Its OPE contains protected multiplets and long multiplets. The protected part is fixed by symmetry and nonrenormalization; the long-multiplet part depends on $\lambda$ and $N$.

This is the transition point from protected AdS/CFT checks to dynamical AdS/CFT physics. The same external operator $\mathcal O_2$ can be used to extract:

$$
\text{protected data}
\quad + \quad
\text{stringy corrections}
\quad + \quad
\text{bulk locality constraints}.
$$

That is why the stress-tensor multiplet four-point function is so central.

## Large-$N$ interpretation

In the large-$N$ limit, normalized single-trace chiral primaries behave like single-particle states in AdS. Schematically, for unit-normalized single-trace operators,

$$
\left\langle \mathcal O_p\mathcal O_p\right\rangle \sim 1,
\qquad
\left\langle \mathcal O_{p_1}\mathcal O_{p_2}\mathcal O_{p_3}\right\rangle \sim \frac{1}{N},
$$

and connected $k$-point functions scale as

$$
\left\langle \mathcal O_1\cdots \mathcal O_k\right\rangle_{\mathrm{conn}}
\sim N^{2-k}.
$$

This is exactly the scaling expected from tree-level interactions in a weakly coupled bulk theory, where

$$
G_N^{(5)}\sim \frac{1}{N^2}.
$$

Multi-trace half-BPS operators behave like multi-particle states. For instance,

$$
:\!\mathcal O_{p_1}\mathcal O_{p_2}\!:
$$

is a double-trace operator, and at leading large $N$ its dimension is approximately

$$
\Delta=p_1+p_2,
$$

with possible subtleties due to shortening, mixing, and finite-$N$ relations. The general rule is:

$$
\boxed{
\text{single trace} \leftrightarrow \text{single-particle bulk mode},
\qquad
\text{multi trace} \leftrightarrow \text{multi-particle bulk state}.
}
$$

The half-BPS sector makes this rule unusually explicit because dimensions and $R$-symmetry representations are protected.

## Kaluza--Klein dictionary on $S^5$

The internal space $S^5$ has isometry group

$$
SO(6)\simeq SU(4)_R.
$$

Scalar spherical harmonics of degree $p$ on $S^5$ transform as symmetric traceless rank-$p$ tensors of $SO(6)$, hence in the same representation

$$
[0,p,0]
$$

as the CFT chiral primary $\mathcal O_p$.

The corresponding Kaluza--Klein scalar field in $\mathrm{AdS}_5$ has mass

$$
\boxed{m_p^2L^2=p(p-4).}
$$

For a scalar field in $\mathrm{AdS}_{d+1}$, the mass-dimension relation is

$$
m^2L^2=\Delta(\Delta-d).
$$

Here $d=4$, so

$$
m^2L^2=\Delta(\Delta-4).
$$

Substituting $\Delta=p$ gives precisely

$$
m_p^2L^2=p(p-4).
$$

The first few cases are instructive:

| $p$ | CFT operator | $SU(4)_R$ rep | $\Delta$ | $m^2L^2$ | AdS interpretation |
|---:|---|---|---:|---:|---|
| $2$ | $\mathcal O_2^{IJ}$ | $[0,2,0]=\mathbf{20}'$ | $2$ | $-4$ | scalar in graviton multiplet |
| $3$ | $\mathcal O_3$ | $[0,3,0]$ | $3$ | $-3$ | first massive KK multiplet |
| $4$ | $\mathcal O_4$ | $[0,4,0]$ | $4$ | $0$ | massless scalar mode in AdS$_5$ |
| $p>4$ | $\mathcal O_p$ | $[0,p,0]$ | $p$ | $p(p-4)$ | higher KK scalar |

The $p=2$ mass satisfies the Breitenlohner--Freedman bound in $\mathrm{AdS}_5$,

$$
m^2L^2\geq -4.
$$

This is not an accident. The stress-tensor multiplet sits at the bottom of the protected KK tower.

## Sources and one-point functions

For a chiral primary $\mathcal O_p$, the CFT generating functional includes a source term

$$
\delta S_{\mathrm{CFT}}
=\int d^4x\,\phi_{0,p}(x,Y)\mathcal O_p(x,Y).
$$

The AdS/CFT dictionary identifies $\phi_{0,p}$ with the boundary value of the dual bulk scalar $s_p$. Near the boundary of Euclidean $\mathrm{AdS}_5$, using a radial coordinate $z$ with $z=0$ at the boundary, the scalar behaves schematically as

$$
s_p(z,x)
\sim z^{4-p}\phi_{0,p}(x)+z^p A_p(x)+\cdots.
$$

The coefficient $\phi_{0,p}$ is the source. The coefficient $A_p$ is related to the expectation value $\langle\mathcal O_p\rangle$, after holographic renormalization and possible contact-term subtleties.

This is the direct continuation of the source logic from earlier pages:

$$
Z_{\mathrm{CFT}}[\phi_0]
=Z_{\mathrm{string}}[s_p\to z^{4-p}\phi_{0,p}].
$$

At large $N$ and large $\lambda$, the string path integral is approximated by classical type IIB supergravity, and correlators of chiral primaries are computed by differentiating the on-shell supergravity action.

## Why the half-BPS sector is not the whole theory

The half-BPS chiral primary tower is elegant, but it is a small subsector of $\mathcal N=4$ SYM. The full theory contains:

- long single-trace operators dual to string excitations,
- multi-trace operators dual to multi-particle states,
- non-BPS operators with large anomalous dimensions at strong coupling,
- spin-chain sectors at weak coupling,
- thermal states dual to black branes,
- Wilson loops and defect operators,
- finite-$N$ effects dual to quantum gravity and branes.

The protected sector gives the cleanest dictionary, not the complete dictionary. Its true power is that it supplies exact landmarks. Once those landmarks are fixed, one can ask dynamical questions about the unprotected data.

## AdS/CFT checkpoint

The half-BPS dictionary is one of the sharpest pieces of AdS/CFT:

$$
\boxed{
\mathcal O_p(x,Y)
\in [0,p,0],\quad \Delta=p
\quad\longleftrightarrow\quad
s_p(x,z,Y)\ \text{on }\mathrm{AdS}_5,
\quad m_p^2L^2=p(p-4).
}
$$

The $SO(6)_R$ representation on the CFT side is the same as the $S^5$ spherical harmonic representation on the bulk side. The protected dimension $\Delta=p$ is the same number that solves the AdS mass-dimension relation. The large-$N$ scaling of correlators is the same scaling as tree-level bulk interactions.

This is the first place where the abstract CFT data

$$
\{\Delta_i,\ell_i,R_i,C_{ijk},\ldots\}
$$

turn into a recognizable higher-dimensional geometry.

## Common pitfalls

First, $\mathcal O_2^{IJ}$ is not the stress tensor. It is the scalar superconformal primary of the stress-tensor multiplet. The stress tensor appears as a descendant in the same multiplet.

Second, “protected dimension” does not imply “all correlators are free.” Four-point functions of protected operators contain unprotected intermediate operators and are dynamical.

Third, single-trace operators are cleanly single-particle only at large $N$. At finite $N$, trace relations and mixing with multi-trace operators are real issues.

Fourth, the null vector $Y^I$ is not an additional coordinate of spacetime. It is an auxiliary device for $SO(6)_R$ tensor algebra. Its geometric cousin on the bulk side is the $S^5$ harmonic, but $Y$ itself is a polarization variable.

## Exercises

### Exercise 1: Why $Y^2=0$ imposes tracelessness

Let $S^{I_1\cdots I_p}$ be a symmetric tensor of $SO(6)$. Show that the generating polynomial

$$
S(Y)=Y_{I_1}\cdots Y_{I_p}S^{I_1\cdots I_p}
$$

is insensitive to traces of $S$ when restricted to $Y^2=0$.

<details><summary><strong>Solution</strong></summary>

A trace term in $S^{I_1\cdots I_p}$ has the schematic form

$$
\delta^{I_1I_2}A^{I_3\cdots I_p}.
$$

Contracting with $Y_{I_1}\cdots Y_{I_p}$ gives

$$
Y_{I_1}Y_{I_2}\delta^{I_1I_2}\,Y_{I_3}\cdots Y_{I_p}A^{I_3\cdots I_p}
=(Y\cdot Y)Y_{I_3}\cdots Y_{I_p}A^{I_3\cdots I_p}.
$$

On the null cone $Y^2=0$, this contribution vanishes. Therefore $S(Y)$ only remembers the symmetric traceless part of $S$.

</details>

### Exercise 2: Derive the two-point function

Assume $\mathcal O_p(x,Y)$ has dimension $p$ and is homogeneous of degree $p$ in $Y$. Use conformal symmetry and $SO(6)_R$ invariance to derive

$$
\left\langle \mathcal O_p(x_1,Y_1)\mathcal O_q(x_2,Y_2)\right\rangle
\propto
\delta_{pq}\frac{(Y_{12})^p}{(x_{12}^2)^p}.
$$

<details><summary><strong>Solution</strong></summary>

Conformal symmetry fixes the two-point function of scalar primaries to vanish unless their dimensions match. Since $\Delta_p=p$ and $\Delta_q=q$, this gives $p=q$.

For $p=q$, the spacetime dependence must be

$$
\frac{1}{(x_{12}^2)^p}.
$$

The polarization dependence must be invariant under $SO(6)_R$, homogeneous of degree $p$ in $Y_1$, and homogeneous of degree $p$ in $Y_2$. The only available invariant is

$$
Y_{12}=Y_1\cdot Y_2,
$$

so the numerator is $(Y_{12})^p$. The overall constant is fixed by normalization.

</details>

### Exercise 3: Three-point powers

Show that the three-point structure

$$
\frac{
Y_{12}^{\alpha_{12}}
Y_{23}^{\alpha_{23}}
Y_{13}^{\alpha_{13}}
}{
(x_{12}^2)^{\alpha_{12}}
(x_{23}^2)^{\alpha_{23}}
(x_{13}^2)^{\alpha_{13}}
}
$$

has the correct scaling dimension and $R$-symmetry degree at each point if

$$
\alpha_{12}=\frac{p_1+p_2-p_3}{2},
\qquad
\alpha_{23}=\frac{p_2+p_3-p_1}{2},
\qquad
\alpha_{13}=\frac{p_1+p_3-p_2}{2}.
$$

<details><summary><strong>Solution</strong></summary>

At point $1$, the polarization vector $Y_1$ appears in $Y_{12}$ and $Y_{13}$, so its degree is

$$
\alpha_{12}+\alpha_{13}
=\frac{p_1+p_2-p_3}{2}+\frac{p_1+p_3-p_2}{2}
=p_1.
$$

Similarly, the degrees in $Y_2$ and $Y_3$ are $p_2$ and $p_3$.

For spacetime scaling at $x_1$, the denominator contains $(x_{12}^2)^{\alpha_{12}}(x_{13}^2)^{\alpha_{13}}$. The total squared-distance exponent involving $x_1$ is

$$
\alpha_{12}+\alpha_{13}=p_1,
$$

so the correlator has scaling dimension $p_1$ at point $1$. The same argument holds at points $2$ and $3$.

</details>

### Exercise 4: AdS mass from protected dimension

Use the scalar mass-dimension relation in $\mathrm{AdS}_5$,

$$
m^2L^2=\Delta(\Delta-4),
$$

to derive the Kaluza--Klein mass of the field dual to $\mathcal O_p$.

<details><summary><strong>Solution</strong></summary>

For the half-BPS chiral primary,

$$
\Delta=p.
$$

Substituting this into the $\mathrm{AdS}_5$ scalar relation gives

$$
m_p^2L^2=p(p-4).
$$

For $p=2$, this gives $m^2L^2=-4$, which saturates the Breitenlohner--Freedman bound in $\mathrm{AdS}_5$.

</details>

### Exercise 5: Why a protected external operator can have a dynamical four-point function

Explain why the four-point function

$$
\left\langle \mathcal O_2\mathcal O_2\mathcal O_2\mathcal O_2\right\rangle
$$

can depend on the coupling even though $\mathcal O_2$ is half-BPS.

<details><summary><strong>Solution</strong></summary>

The BPS condition protects the external operator dimension and the shortening of the stress-tensor multiplet. It does not imply that every operator appearing in the OPE

$$
\mathcal O_2\times \mathcal O_2
$$

is protected. The OPE contains protected multiplets but also long multiplets. The dimensions and OPE coefficients of long multiplets can depend on the coupling. A four-point function decomposes into conformal blocks for all exchanged multiplets, so the long-multiplet data make the full correlator dynamical.

</details>

## Further reading

For this page, the most useful next references are reviews and lecture notes on $\mathcal N=4$ SYM, superconformal representation theory, and holographic correlators. The essential physics to keep in mind is simple: half-BPS chiral primaries are the protected scalar tower whose dimensions and $SO(6)_R$ representations match the Kaluza--Klein tower of type IIB supergravity on $S^5$.
