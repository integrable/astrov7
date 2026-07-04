---
title: "Cardy formula and black-hole entropy"
description: "How modular invariance and the Brown–Henneaux central charge reproduce the Bekenstein–Hawking entropy of BTZ black holes."
sidebar:
  order: 40
---

The BTZ black hole entropy is

$$
S_{\mathrm{BTZ}}
=
\frac{2\pi r_+}{4G_3}.
$$

The Cardy formula says that a two-dimensional conformal field theory has a universal asymptotic density of high-energy states controlled by its central charge. Combining this universal CFT statement with the Brown–Henneaux central charge,

$$
c=\bar c=\frac{3L}{2G_3},
$$

one exactly reproduces the BTZ entropy.

This calculation is one of the sharpest early successes of AdS$_3$/CFT$_2$. It does not require detailed knowledge of the microscopic CFT. It uses only symmetry, modular invariance, and the relation between gravitational charges and Virasoro zero modes.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic pipeline from Brown-Henneaux central charge and BTZ charges through the Cardy formula to the Bekenstein-Hawking entropy.](/figures/course/cardy-btz-entropy.svg)

<figcaption>

The BTZ entropy match has three inputs: the Brown–Henneaux central charge $c=\bar c=3L/(2G_3)$, the charge map $L_0-c/24=(ML+J)/2$ and $\bar L_0-\bar c/24=(ML-J)/2$, and the Cardy formula for the high-energy density of states in a modular-invariant CFT$_2$. The output is $S=2\pi r_+/(4G_3)$.

</figcaption>
</figure>

## Why this matters

For a black hole, the gravitational entropy is geometric:

$$
S_{\mathrm{BH}}=\frac{A}{4G}.
$$

In three dimensions the horizon “area” is the horizon circumference,

$$
A=2\pi r_+.
$$

So the BTZ entropy is

$$
S_{\mathrm{BTZ}}
=
\frac{\pi r_+}{2G_3}.
$$

A microscopic explanation should identify a quantum Hilbert space and count the states responsible for this entropy.

AdS$_3$/CFT$_2$ gives such a count. The boundary theory is a two-dimensional CFT. Its asymptotic density of states is not arbitrary; modular invariance of the torus partition function relates the high-temperature regime to the low-temperature vacuum. The result is the Cardy formula.

The astonishing point is that the resulting entropy depends only on the central charge and the conserved charges. Since Brown and Henneaux fixed the central charge from asymptotic symmetry, the entropy follows.

## CFT on the cylinder

Put the CFT on a spatial circle of radius $L$:

$$
(t,\phi)\in \mathbb R\times S^1,
\qquad
\phi\sim\phi+2\pi.
$$

The Hamiltonian and angular momentum are

$$
H
=
\frac{1}{L}
\left(
L_0+\bar L_0-\frac{c+\bar c}{24}
\right),
\qquad
J_{\mathrm{CFT}}
=
L_0-\bar L_0.
$$

The shifts by $c/24$ and $\bar c/24$ are not optional. They are the Casimir-energy shifts coming from the map between the plane and the cylinder.

For parity-invariant Einstein gravity in AdS$_3$,

$$
c=\bar c=\frac{3L}{2G_3}.
$$

The global AdS$_3$ vacuum corresponds to

$$
L_0=\bar L_0=0.
$$

Then the cylinder energy is

$$
H_{\mathrm{vac}}
=
-\frac{c}{12L}
=
-\frac{1}{8G_3},
$$

which matches the mass of global AdS$_3$.

This is the first place where the $c/24$ shift visibly matters.

## The Cardy formula

For a unitary, modular-invariant two-dimensional CFT with sufficiently well-behaved low-energy spectrum, the high-energy density of states obeys the Cardy formula. In the microcanonical form relevant for rotating BTZ black holes,

$$
S(h,\bar h)
\simeq
2\pi\sqrt{\frac{c}{6}\left(h-\frac{c}{24}\right)}
+
2\pi\sqrt{\frac{\bar c}{6}\left(\bar h-\frac{\bar c}{24}\right)},
$$

where

$$
h=L_0,
\qquad
\bar h=\bar L_0,
$$

and the formula is valid when the shifted weights are large compared with the vacuum scale.

It is often cleaner to define

$$
\Delta_R
=
L_0-\frac{c}{24},
\qquad
\Delta_L
=
\bar L_0-\frac{\bar c}{24}.
$$

Then

$$
S
\simeq
2\pi\sqrt{\frac{c\Delta_R}{6}}
+
2\pi\sqrt{\frac{\bar c\Delta_L}{6}}.
$$

The labels $L$ and $R$ are conventional; some authors interchange them. What matters is the pair of independent Virasoro sectors.

## Sketch of the modular derivation

The Euclidean finite-temperature CFT lives on a torus. For a nonrotating ensemble, the partition function is

$$
Z(\beta)
=
\mathrm{Tr}\,e^{-\beta H},
\qquad
H
=
\frac{1}{L}
\left(
L_0+\bar L_0-\frac{c+\bar c}{24}
\right).
$$

The torus modular parameter is purely imaginary,

$$
\tau=\frac{i\beta}{2\pi L}.
$$

Modular invariance states that the torus partition function is invariant under

$$
\tau\longrightarrow -\frac{1}{\tau}.
$$

For imaginary $\tau$, this relates

$$
\beta
\longrightarrow
\frac{4\pi^2L^2}{\beta}.
$$

Thus the high-temperature limit $\beta\ll L$ is related to the low-temperature limit $4\pi^2L^2/\beta\gg L$.

At low temperature, the partition function is dominated by the vacuum. For $c=\bar c$,

$$
E_0=-\frac{c}{12L},
$$

so the modular-transformed partition function gives

$$
\log Z(\beta)
\simeq
\frac{\pi^2cL}{3\beta}.
$$

The thermal entropy is

$$
S
=
\left(1-\beta\frac{\partial}{\partial\beta}\right)\log Z,
$$

so

$$
S
\simeq
\frac{2\pi^2cL}{3\beta}
=
\frac{2\pi^2cL}{3}T.
$$

This is the canonical Cardy formula for a parity-invariant CFT on a circle of radius $L$.

The rotating case is the same logic applied separately to left- and right-moving sectors.

## Rotating ensemble and chiral temperatures

For a rotating BTZ black hole, the boundary density matrix is

$$
\rho
\propto
\exp\left[-\beta\left(H-\Omega J_{\mathrm{CFT}}\right)\right].
$$

It is useful to write this in chiral form. Define

$$
T_R
=
\frac{r_+ + r_-}{2\pi L^2},
\qquad
T_L
=
\frac{r_+ - r_-}{2\pi L^2}.
$$

Then the canonical Cardy entropy is

$$
S
=
\frac{\pi^2L}{3}\left(cT_R+\bar cT_L\right).
$$

For $c=\bar c=3L/(2G_3)$,

$$
S
=
\frac{\pi^2L}{3}\frac{3L}{2G_3}
\left(
\frac{r_+ + r_-}{2\pi L^2}
+
\frac{r_+ - r_-}{2\pi L^2}
\right).
$$

The $r_-$ terms cancel, leaving

$$
S
=
\frac{\pi r_+}{2G_3}
=
\frac{2\pi r_+}{4G_3}.
$$

This is the Bekenstein–Hawking entropy of the rotating BTZ black hole.

## Microcanonical match

Now do the same calculation in microcanonical language. The BTZ charge map is

$$
L_0-\frac{c}{24}
=
\frac{ML+J}{2},
\qquad
\bar L_0-\frac{\bar c}{24}
=
\frac{ML-J}{2}.
$$

Using

$$
M
=
\frac{r_+^2+r_-^2}{8G_3L^2},
\qquad
J
=
\frac{r_+r_-}{4G_3L},
$$

we get

$$
ML+J
=
\frac{(r_+ + r_-)^2}{8G_3L},
$$

and

$$
ML-J
=
\frac{(r_+ - r_-)^2}{8G_3L}.
$$

Therefore

$$
\Delta_R
=
L_0-\frac{c}{24}
=
\frac{(r_+ + r_-)^2}{16G_3L},
$$

and

$$
\Delta_L
=
\bar L_0-\frac{\bar c}{24}
=
\frac{(r_+ - r_-)^2}{16G_3L}.
$$

Insert these into Cardy's formula:

$$
S
=
2\pi\sqrt{\frac{c\Delta_R}{6}}
+
2\pi\sqrt{\frac{\bar c\Delta_L}{6}}.
$$

With

$$
c=\bar c=\frac{3L}{2G_3},
$$

we have

$$
\frac{c\Delta_R}{6}
=
\frac{L}{4G_3}
\frac{(r_+ + r_-)^2}{16G_3L}
=
\frac{(r_+ + r_-)^2}{64G_3^2},
$$

and similarly

$$
\frac{\bar c\Delta_L}{6}
=
\frac{(r_+ - r_-)^2}{64G_3^2}.
$$

Thus

$$
S
=
2\pi
\left(
\frac{r_+ + r_-}{8G_3}
+
\frac{r_+ - r_-}{8G_3}
\right)
=
\frac{2\pi r_+}{4G_3}.
$$

This is the exact Bekenstein–Hawking entropy.

## Nonrotating BTZ as a warm-up

For $r_-=0$,

$$
M=\frac{r_+^2}{8G_3L^2},
\qquad
J=0.
$$

The shifted weights are equal:

$$
\Delta_R=\Delta_L=\frac{ML}{2}=\frac{r_+^2}{16G_3L}.
$$

Cardy's formula gives

$$
S
=
4\pi\sqrt{\frac{c}{6}\frac{r_+^2}{16G_3L}}.
$$

Using $c=3L/(2G_3)$,

$$
S
=
4\pi\sqrt{\frac{L}{4G_3}\frac{r_+^2}{16G_3L}}
=
4\pi\frac{r_+}{8G_3}
=
\frac{\pi r_+}{2G_3}.
$$

Again,

$$
S=\frac{2\pi r_+}{4G_3}.
$$

## Extremal BTZ and chiral Cardy

In the extremal limit

$$
r_+=r_-.
$$

Then

$$
T_L=0,
\qquad
T_R=\frac{r_+}{\pi L^2},
$$

in our naming convention. The entropy is entirely carried by one chiral sector:

$$
S
=
\frac{\pi^2L}{3}cT_R
=
\frac{\pi r_+}{2G_3}.
$$

In microcanonical form,

$$
\Delta_L=0,
\qquad
\Delta_R=\frac{r_+^2}{4G_3L}.
$$

Then

$$
S
=
2\pi\sqrt{\frac{c\Delta_R}{6}}.
$$

Extremal BTZ is therefore a particularly clean example of a chiral high-energy state in a two-dimensional CFT.

## What exactly is being counted?

The most conservative answer is:

$$
\text{Cardy counts the asymptotic density of states of the boundary CFT.}
$$

In AdS$_3$ gravity, Brown–Henneaux boundary conditions imply that the asymptotic symmetry algebra is two copies of the Virasoro algebra with central charge $c=3L/(2G_3)$. The BTZ black hole has definite values of the charges $L_0$ and $\bar L_0$. If the quantum theory is a modular-invariant CFT with the appropriate spectrum, then Cardy's formula gives the degeneracy of states with those charges.

This is a microscopic entropy in the boundary description. It does not necessarily display individual horizon microstates in a local bulk basis. In fact, one of the lessons of holography is that a local bulk description is often the wrong language for counting all the states.

The entropy match is nevertheless extremely strong: the same number is obtained from the horizon area and from universal CFT asymptotics.

## Why the match is universal

The calculation used only three ingredients:

1. the asymptotic symmetry algebra of AdS$_3$ gravity;
2. the charge map between BTZ parameters and Virasoro zero modes;
3. modular invariance of the boundary CFT partition function.

This is why the BTZ entropy calculation is so robust. It does not depend on knowing a Lagrangian for the boundary CFT, nor on supersymmetry, nor on weak coupling.

At the same time, this robustness has a cost: the Cardy formula gives a degeneracy, not a simple list of bulk microstates. It counts states from the boundary perspective.

## Conditions and caveats

The Cardy formula is universal, but not magic. Its use assumes a suitable two-dimensional CFT.

Important assumptions include:

- a well-defined Hilbert space on the circle;
- modular invariance of the torus partition function;
- a normalizable vacuum;
- sufficiently sparse or controlled low-energy spectrum in the regime of interest;
- large enough charges for the asymptotic formula to apply.

For semiclassical BTZ black holes, the relevant limit is

$$
c\gg 1,
\qquad
\Delta_L,\Delta_R\sim c.
$$

This is the black-hole regime. Small conical defects and light states require more detailed information about the CFT spectrum.

Another caveat is that pure three-dimensional gravity may not be a fully consistent standalone quantum theory with exactly the spectrum one might naively expect. In string-theoretic AdS$_3$ examples, additional sectors are often present. The Cardy match is universal, but the microscopic interpretation can differ among theories.

## Relation to the Hawking–Page transition

For global AdS$_3$, the boundary CFT lives on a circle. Thermal AdS$_3$ and Euclidean BTZ are two different bulk fillings of the same boundary torus. The Hawking–Page transition is a modular transition between which cycle of the boundary torus is contractible in the bulk.

In the CFT, the same physics is encoded in modular invariance:

$$
\text{low temperature vacuum dominance}
\quad
\longleftrightarrow
\quad
\text{high temperature Cardy growth}.
$$

This is one reason AdS$_3$/CFT$_2$ is so sharp: the gravitational saddle competition and the CFT modular transformation are two views of the same torus geometry.

## Dictionary checkpoint

The entropy calculation can be summarized as:

$$
\boxed{
\begin{aligned}
\mathrm{AdS}_3\text{ gravity}
&\Rightarrow
c=\bar c=\frac{3L}{2G_3},
\\
\mathrm{BTZ}(M,J)
&\Rightarrow
\Delta_R=\frac{ML+J}{2},
\quad
\Delta_L=\frac{ML-J}{2},
\\
\mathrm{CFT}_2\text{ Cardy}
&\Rightarrow
S=2\pi\sqrt{\frac{c\Delta_R}{6}}
+2\pi\sqrt{\frac{\bar c\Delta_L}{6}},
\\
&\Rightarrow
S=\frac{2\pi r_+}{4G_3}.
\end{aligned}
}
$$

This is the AdS$_3$/CFT$_2$ black-hole entropy match in its most compact form.

## Common confusions

### “Cardy's formula counts gravitons in the BTZ exterior.”

Not exactly. Pure three-dimensional gravity has no local graviton modes. Cardy's formula counts boundary CFT states with the same conserved charges as the BTZ black hole. The bulk interpretation may involve boundary gravitons, quotient sectors, stringy degrees of freedom, or other microscopic variables depending on the full theory.

### “The $c/24$ shift is a convention that can be ignored.”

The shift is physically meaningful on the cylinder. It accounts for the vacuum Casimir energy. Without it, global AdS$_3$ would not map to the CFT vacuum correctly.

### “The entropy depends on $r_-$, because rotating BTZ has two horizons.”

The left and right sectors separately depend on $r_-$, but the sum in the entropy depends only on $r_+$:

$$
(r_+ + r_-)+(r_+ - r_-)=2r_+.
$$

The outer horizon controls the Bekenstein–Hawking entropy.

### “The Cardy formula is exact for every energy.”

No. It is an asymptotic high-energy formula. In special theories there can be exact refinements or protected versions, but the usual Cardy formula is a universal asymptotic statement.

### “The match proves pure Einstein gravity in AdS$_3$ is a complete quantum theory.”

No. The entropy match is a powerful consistency check, but the existence and uniqueness of a fully consistent pure-gravity CFT dual is a deeper question. The Cardy calculation tells us what any suitable dual must reproduce in the black-hole regime.

## Exercises

### Exercise 1: The nonrotating Cardy match

For $J=0$, show directly that the Cardy formula reproduces

$$
S_{\mathrm{BTZ}}=\frac{2\pi r_+}{4G_3}.
$$

<details>
<summary><strong>Solution</strong></summary>

For $J=0$,

$$
M=\frac{r_+^2}{8G_3L^2},
$$

and

$$
\Delta_R=\Delta_L=\frac{ML}{2}=\frac{r_+^2}{16G_3L}.
$$

With $c=\bar c=3L/(2G_3)$,

$$
\frac{c\Delta_R}{6}
=
\frac{L}{4G_3}\frac{r_+^2}{16G_3L}
=
\frac{r_+^2}{64G_3^2}.
$$

Both sectors contribute equally, so

$$
S
=
2\left(2\pi\frac{r_+}{8G_3}\right)
=
\frac{\pi r_+}{2G_3}
=
\frac{2\pi r_+}{4G_3}.
$$

</details>

### Exercise 2: Rotating BTZ entropy

Starting from

$$
\Delta_R=\frac{(r_+ + r_-)^2}{16G_3L},
\qquad
\Delta_L=\frac{(r_+ - r_-)^2}{16G_3L},
$$

derive the BTZ entropy.

<details>
<summary><strong>Solution</strong></summary>

Using $c=\bar c=3L/(2G_3)$,

$$
\sqrt{\frac{c\Delta_R}{6}}
=
\sqrt{
\frac{L}{4G_3}\frac{(r_+ + r_-)^2}{16G_3L}
}
=
\frac{r_+ + r_-}{8G_3},
$$

and

$$
\sqrt{\frac{\bar c\Delta_L}{6}}
=
\frac{r_+ - r_-}{8G_3}.
$$

Therefore

$$
S
=
2\pi\left(\frac{r_+ + r_-}{8G_3}+\frac{r_+ - r_-}{8G_3}\right)
=
\frac{\pi r_+}{2G_3}
=
\frac{2\pi r_+}{4G_3}.
$$

</details>

### Exercise 3: Canonical Cardy formula

Use

$$
S=\frac{\pi^2L}{3}\left(cT_R+\bar cT_L\right),
$$

with

$$
T_R=\frac{r_+ + r_-}{2\pi L^2},
\qquad
T_L=\frac{r_+ - r_-}{2\pi L^2},
$$

to reproduce the BTZ entropy.

<details>
<summary><strong>Solution</strong></summary>

For Einstein gravity,

$$
c=\bar c=\frac{3L}{2G_3}.
$$

Then

$$
S
=
\frac{\pi^2L}{3}\frac{3L}{2G_3}
\left(
\frac{r_+ + r_-}{2\pi L^2}
+
\frac{r_+ - r_-}{2\pi L^2}
\right).
$$

The expression in parentheses is

$$
\frac{2r_+}{2\pi L^2}=\frac{r_+}{\pi L^2}.
$$

Hence

$$
S
=
\frac{\pi^2L}{3}\frac{3L}{2G_3}\frac{r_+}{\pi L^2}
=
\frac{\pi r_+}{2G_3}
=
\frac{2\pi r_+}{4G_3}.
$$

</details>

### Exercise 4: The role of the vacuum shift

Show that global AdS$_3$ maps to the CFT vacuum if

$$
M=-\frac{1}{8G_3},
\qquad
J=0,
\qquad
c=\frac{3L}{2G_3}.
$$

<details>
<summary><strong>Solution</strong></summary>

The charge map is

$$
L_0-\frac{c}{24}=\frac{ML+J}{2}.
$$

For global AdS$_3$,

$$
\frac{ML+J}{2}
=
-\frac{L}{16G_3}.
$$

But

$$
\frac{c}{24}
=
\frac{1}{24}\frac{3L}{2G_3}
=
\frac{L}{16G_3}.
$$

Therefore

$$
L_0-\frac{c}{24}=-\frac{c}{24},
$$

which gives

$$
L_0=0.
$$

The same argument gives $\bar L_0=0$. Thus global AdS$_3$ maps to the CFT vacuum.

</details>

## Further reading

- J. L. Cardy, [Operator Content of Two-Dimensional Conformally Invariant Theories](https://www.sciencedirect.com/science/article/abs/pii/0550321386905523).
- A. Strominger, [Black Hole Entropy from Near-Horizon Microstates](https://arxiv.org/abs/hep-th/9712251).
- S. Carlip, [What We Don't Know about BTZ Black Hole Entropy](https://arxiv.org/abs/hep-th/9806026).
- M. Bañados, C. Teitelboim, and J. Zanelli, [The Black Hole in Three Dimensional Space Time](https://arxiv.org/abs/hep-th/9204099).
- J. D. Brown and M. Henneaux, [Central Charges in the Canonical Realization of Asymptotic Symmetries](https://ui.adsabs.harvard.edu/abs/1986CMaPh.104..207B/abstract).
