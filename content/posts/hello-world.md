---
title: "A Tour of Mathematical Physics: From Fields to Strings"
date: 2024-01-15
tags: ["QFT", "string theory", "mathematics", "gauge theory"]
summary: "An introduction to the mathematical language of theoretical physics — from the action principle and Lagrangian mechanics to quantum fields and the string worldsheet."
---

## Introduction

Theoretical physics lives in the language of mathematics. Whether you're computing scattering amplitudes in quantum chromodynamics or studying the geometry of Calabi–Yau manifolds in string theory, the underlying machinery is built from the same elegant structures: differential geometry, complex analysis, representation theory, and functional calculus.

This post is a brief tour of some key ideas, illustrated with the equations I find most beautiful.

---

## The Action Principle

Everything in classical mechanics follows from a single principle: the **stationary action principle**. Given a Lagrangian $\mathcal{L}(q, \dot{q}, t)$, the action is

$$S[q] = \int_{t_1}^{t_2} \mathcal{L}(q, \dot{q}, t)\, dt$$

Physical trajectories are those for which $\delta S = 0$, which yields the **Euler–Lagrange equations**:

$$\frac{d}{dt}\frac{\partial \mathcal{L}}{\partial \dot{q}^i} - \frac{\partial \mathcal{L}}{\partial q^i} = 0$$

In field theory, $q^i(t)$ is replaced by a field $\phi(x^\mu)$ and the Lagrangian becomes a Lagrangian *density* $\mathcal{L}(\phi, \partial_\mu \phi)$, so the action becomes

$$S[\phi] = \int d^4x\, \mathcal{L}(\phi, \partial_\mu \phi)$$

---

## The Klein–Gordon and Dirac Fields

The simplest relativistic scalar field theory is described by the **Klein–Gordon Lagrangian**:

$$\mathcal{L} = \frac{1}{2}(\partial_\mu \phi)(\partial^\mu \phi) - \frac{1}{2}m^2 \phi^2$$

which gives the equation of motion

$$(\Box + m^2)\phi = 0, \qquad \Box \equiv \partial_\mu \partial^\mu = \partial_t^2 - \nabla^2$$

For spin-$\frac{1}{2}$ particles, the **Dirac equation** takes the elegant form

$$( i\hbar \gamma^\mu \partial_\mu - mc )\psi = 0$$

where $\gamma^\mu$ are the Dirac matrices satisfying the Clifford algebra $\{\gamma^\mu, \gamma^\nu\} = 2g^{\mu\nu}$.

---

## Gauge Theory and the Standard Model

The Standard Model is a gauge theory based on the gauge group $SU(3) \times SU(2) \times U(1)$. For a $U(1)$ gauge theory (electrodynamics), the gauge-invariant Lagrangian is

$$\mathcal{L} = -\frac{1}{4}F_{\mu\nu}F^{\mu\nu} + \bar{\psi}(i\gamma^\mu D_\mu - m)\psi$$

where $F_{\mu\nu} = \partial_\mu A_\nu - \partial_\nu A_\mu$ is the field strength tensor and $D_\mu = \partial_\mu + ieA_\mu$ is the covariant derivative.

For a non-Abelian gauge group $G$ with gauge field $A_\mu = A_\mu^a T^a$, the field strength becomes

$$F_{\mu\nu}^a = \partial_\mu A_\nu^a - \partial_\nu A_\mu^a + g f^{abc} A_\mu^b A_\nu^c$$

where $f^{abc}$ are the structure constants of $G$.

---

## Einstein's Field Equations

General relativity follows from the **Einstein–Hilbert action**:

$$S = \frac{1}{16\pi G} \int d^4x\, \sqrt{-g}\, R + S_{\text{matter}}$$

where $g = \det(g_{\mu\nu})$ is the metric determinant and $R = g^{\mu\nu}R_{\mu\nu}$ is the Ricci scalar. Varying with respect to $g^{\mu\nu}$ gives **Einstein's field equations**:

$$G_{\mu\nu} \equiv R_{\mu\nu} - \frac{1}{2}g_{\mu\nu}R = 8\pi G\, T_{\mu\nu}$$

This single tensor equation encodes how matter curves spacetime and how that curvature determines the motion of matter — gravity is geometry.

---

## The Path Integral

In quantum mechanics, the Feynman **path integral** formulation replaces classical trajectories with a sum over all paths:

$$\langle x_f, t_f | x_i, t_i \rangle = \int \mathcal{D}x\, e^{\frac{i}{\hbar} S[x]}$$

In quantum field theory, this generalizes to a functional integral over field configurations:

$$Z = \int \mathcal{D}\phi\, e^{iS[\phi]/\hbar}$$

The generating functional $Z[J]$ with a source $J$ encodes all correlation functions:

$$Z[J] = \int \mathcal{D}\phi\, \exp\!\left(iS[\phi] + i\int d^4x\, J(x)\phi(x)\right)$$

The $n$-point functions are obtained by functional differentiation:

$$\langle \phi(x_1)\cdots\phi(x_n)\rangle = \frac{1}{Z[0]} \frac{\delta^n Z[J]}{\delta J(x_1)\cdots \delta J(x_n)}\bigg|_{J=0}$$

---

## Strings and the Polyakov Action

In string theory, the fundamental objects are one-dimensional strings sweeping out a **worldsheet** $\Sigma$ in spacetime. The dynamics are governed by the **Polyakov action**:

$$S_P = -\frac{T}{2}\int_\Sigma d^2\sigma\, \sqrt{-h}\, h^{ab}\partial_a X^\mu \partial_b X_\mu$$

where $h_{ab}$ is the worldsheet metric, $X^\mu(\sigma, \tau)$ are the embedding coordinates, and $T = 1/(2\pi\alpha')$ is the string tension.

The critical dimension for the bosonic string is $D = 26$, while for the superstring it is $D = 10$. The requirement of conformal invariance on the worldsheet — specifically the vanishing of the Weyl anomaly — forces this constraint.

The mass spectrum of the open bosonic string in light-cone gauge is:

$$m^2 = \frac{1}{\alpha'}\left(N - 1\right)$$

where $N = \sum_{n=1}^{\infty} \alpha_{-n} \cdot \alpha_n$ is the number operator. The ground state $N=0$ gives a tachyon with $m^2 = -1/\alpha'$, while the first excited level $N=1$ gives a massless vector — the photon.

---

## The AdS/CFT Correspondence

Perhaps the most profound duality in modern theoretical physics is the **AdS/CFT correspondence** (Maldacena, 1997):

> Type IIB superstring theory on $AdS_5 \times S^5$ is dual to $\mathcal{N}=4$ super-Yang–Mills theory in $4d$.

In its most compact form, the dictionary reads

$$Z_{\text{string}}\!\left[\phi_0\right] = \left\langle \exp\!\left(\int d^4x\, \phi_0(x)\,\mathcal{O}(x)\right)\right\rangle_{\text{CFT}}$$

This identifies the bulk-to-boundary limit of string fields with sources for operators in the boundary CFT. It gives us a precise non-perturbative definition of quantum gravity in asymptotically anti-de Sitter space.

---

## Closing Thoughts

The equations above are just a small window into the rich landscape of theoretical physics. What strikes me most is the unity behind it all — the same ideas of symmetry, action, and quantization appear everywhere, from a simple harmonic oscillator to the structure of spacetime itself.

If you have questions or want to discuss any of these topics, feel free to reach out.
